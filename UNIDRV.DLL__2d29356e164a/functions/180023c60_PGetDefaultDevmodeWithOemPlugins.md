# PGetDefaultDevmodeWithOemPlugins

- ea: `0x180023c60`
- end: `0x180023dc6`
- name: `PGetDefaultDevmodeWithOemPlugins`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x18002540c`

## callees

- `0x180023c60`
- `0x18003401c`
- `0x1800340ac`
- `0x18003d1c4`
- `0x1800405d8`
- `0x1800732a0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180023da7`
- `KERNEL32!LocalFree` at `0x180023da7`
- `KERNEL32!LocalAlloc` at `0x180023d3c`
- `KERNEL32!LocalAlloc` at `0x180023d3c`

## pseudocode

```c
struct _devicemodeW *__fastcall PGetDefaultDevmodeWithOemPlugins(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        __int64 *a6,
        void *a7)
{
  int v10; // eax
  unsigned int v11; // edi
  unsigned int v12; // ecx
  unsigned int v13; // esi
  unsigned int v14; // ebp
  struct _devicemodeW *v15; // rax
  struct _devicemodeW *v16; // rbx
  void *v17; // rcx
  unsigned int v19; // [rsp+60h] [rbp+8h] BYREF
  int v20; // [rsp+64h] [rbp+Ch]
  __int64 v21; // [rsp+78h] [rbp+20h] BYREF

  v20 = HIDWORD(a1);
  v19 = 0;
  v21 = 0;
  if ( a4 )
  {
    v10 = 0;
    if ( *(_DWORD *)(a4 + 4) == 1196442656 )
    {
      v11 = 1;
    }
    else
    {
      v11 = 0;
      if ( *(_DWORD *)(a4 + 4) != 1347437600 )
        v10 = -2147418113;
    }
    if ( v10 >= 0 && (int)GetDevmodeGlobals(v11, 0, 0, &v21) >= 0 )
    {
      v12 = *(unsigned __int16 *)(v21 + 2) + 220;
      v13 = v12 + a2;
      if ( v12 + a2 >= v12 )
      {
        if ( (unsigned int)BCalcTotalOEMDMSize((__int64)a7, a6, &v19) )
        {
          v14 = v19;
          if ( v13 + v19 >= v19 )
          {
            v15 = (struct _devicemodeW *)LocalAlloc(0x40u, v13 + v19);
            v16 = v15;
            if ( v15 )
            {
              if ( (unsigned int)UniBInitDriverDefaultDevmode((__int64)v15, (void *)a5, a3, a4, a5)
                && (unsigned int)BInitOemPluginDefaultDevmode(a7, v16, (struct _OEM_DMEXTRAHEADER *)((char *)v16 + v13))
                && (int)PatchDevmodeSizeFieldsAndJTHdr(v17, v16, a2, v14, v11) >= 0 )
              {
                return v16;
              }
              LocalFree(v16);
            }
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180023c60  mov     rax, rsp
0x180023c63  mov     [rax+10h], rbx
0x180023c67  mov     [rax+18h], rbp
0x180023c6b  mov     [rax+8], rcx
0x180023c6f  push    rsi
0x180023c70  push    rdi
0x180023c71  push    r12
0x180023c73  push    r14
0x180023c75  push    r15
0x180023c77  sub     rsp, 30h
0x180023c7b  mov     dword ptr [rax+8], 0
0x180023c82  mov     r14, r9
0x180023c85  mov     qword ptr [rax+20h], 0
0x180023c8d  mov     r12, r8
0x180023c90  mov     r15d, edx
0x180023c93  test    r9, r9
0x180023c96  jz      loc_180023DAD
0x180023c9c  xor     eax, eax
0x180023c9e  cmp     dword ptr [r9+4], 47504420h
0x180023ca6  jz      short loc_180023CBB
0x180023ca8  xor     edi, edi
0x180023caa  cmp     dword ptr [r9+4], 50504420h
0x180023cb2  jz      short loc_180023CC0
0x180023cb4  mov     eax, 8000FFFFh
0x180023cb9  jmp     short loc_180023CC0
0x180023cbb  mov     edi, 1
0x180023cc0  test    eax, eax
0x180023cc2  js      loc_180023DAD
0x180023cc8  lea     r9, [rsp+58h+arg_18]
0x180023ccd  xor     r8d, r8d
0x180023cd0  xor     edx, edx
0x180023cd2  mov     ecx, edi
0x180023cd4  call    GetDevmodeGlobals
0x180023cd9  test    eax, eax
0x180023cdb  js      loc_180023DAD
0x180023ce1  mov     rax, [rsp+58h+arg_18]
0x180023ce6  movzx   ecx, word ptr [rax+2]
0x180023cea  add     ecx, 0DCh
0x180023cf0  cmp     ecx, 0DCh
0x180023cf6  jb      loc_180023DAD
0x180023cfc  lea     esi, [rcx+r15]
0x180023d00  cmp     esi, ecx
0x180023d02  jb      loc_180023DAD
0x180023d08  mov     rdx, [rsp+58h+arg_28]
0x180023d10  lea     r8, [rsp+58h+arg_0]
0x180023d15  mov     rcx, [rsp+58h+arg_30]
0x180023d1d  call    BCalcTotalOEMDMSize
0x180023d22  test    eax, eax
0x180023d24  jz      loc_180023DAD
0x180023d2a  mov     ebp, [rsp+58h+arg_0]
0x180023d2e  lea     eax, [rsi+rbp]
0x180023d31  cmp     eax, ebp
0x180023d33  jb      short loc_180023DAD
0x180023d35  mov     edx, eax; uBytes
0x180023d37  mov     ecx, 40h ; '@'; uFlags
0x180023d3c  call    cs:__imp_LocalAlloc
0x180023d42  mov     rbx, rax
0x180023d45  test    rax, rax
0x180023d48  jz      short loc_180023DAD
0x180023d4a  mov     edx, [rsp+58h+arg_20]
0x180023d51  mov     r9, r14
0x180023d54  mov     r8, r12
0x180023d57  mov     [rsp+58h+var_38], edx
0x180023d5b  mov     rcx, rax
0x180023d5e  call    UniBInitDriverDefaultDevmode
0x180023d63  test    eax, eax
0x180023d65  jz      short loc_180023DA4
0x180023d67  mov     r9, [rsp+58h+arg_28]
0x180023d6f  mov     rdx, rbx; struct _devicemodeW *
0x180023d72  mov     rcx, [rsp+58h+arg_30]; void *
0x180023d7a  mov     r8d, esi
0x180023d7d  add     r8, rbx; struct _OEM_DMEXTRAHEADER *
0x180023d80  call    BInitOemPluginDefaultDevmode
0x180023d85  test    eax, eax
0x180023d87  jz      short loc_180023DA4
0x180023d89  mov     r9d, ebp; unsigned int
0x180023d8c  mov     [rsp+58h+var_38], edi; int
0x180023d90  mov     r8d, r15d; unsigned int
0x180023d93  mov     rdx, rbx; struct _devicemodeW *
0x180023d96  call    ?PatchDevmodeSizeFieldsAndJTHdr@@YAJPEAXPEAU_devicemodeW@@KKH@Z; PatchDevmodeSizeFieldsAndJTHdr(void *,_devicemodeW *,ulong,ulong,int)
0x180023d9b  test    eax, eax
0x180023d9d  js      short loc_180023DA4
0x180023d9f  mov     rax, rbx
0x180023da2  jmp     short loc_180023DAF
0x180023da4  mov     rcx, rbx; hMem
0x180023da7  call    cs:__imp_LocalFree
0x180023dad  xor     eax, eax
0x180023daf  mov     rbx, [rsp+58h+arg_8]
0x180023db4  mov     rbp, [rsp+58h+arg_10]
0x180023db9  add     rsp, 30h
0x180023dbd  pop     r15
0x180023dbf  pop     r14
0x180023dc1  pop     r12
0x180023dc3  pop     rdi
0x180023dc4  pop     rsi
0x180023dc5  retn
```
