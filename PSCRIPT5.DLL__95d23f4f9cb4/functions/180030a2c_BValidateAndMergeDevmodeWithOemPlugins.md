# BValidateAndMergeDevmodeWithOemPlugins

- ea: `0x180030a2c`
- end: `0x180030bc6`
- name: `BValidateAndMergeDevmodeWithOemPlugins`
- size: `410`
- prototype: `__int64 __usercall@<rax>(struct _devicemodeW *@<rcx>, __int64, __int64, unsigned int, struct _devicemodeW *, struct _OEM_PLUGINS *, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800033f4`

## callees

- `0x180028c30`
- `0x18002fd80`
- `0x18003005c`
- `0x180030a2c`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180030ba6`
- `KERNEL32!LocalFree` at `0x180030ba6`

## pseudocode

```c
__int64 __fastcall BValidateAndMergeDevmodeWithOemPlugins(
        struct _devicemodeW *a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        unsigned int a7,
        struct _devicemodeW *Src,
        struct _OEM_PLUGINS *a9,
        void *a10)
{
  struct _devicemodeW *v10; // rsi
  int v16; // ecx
  int v17; // eax
  struct _OEM_PLUGINS *v18; // r15
  struct _devicemodeW *v19; // rax
  struct _devicemodeW *v20; // rbp
  unsigned int v21; // edi
  int v22; // esi
  __int64 v23; // rax
  struct _OEM_DMEXTRAHEADER *v24; // r12
  struct _OEM_DMEXTRAHEADER *v25; // r14
  struct _OEM_PLUGIN_ENTRY *v26; // rdi
  __int64 v27; // rax

  v10 = Src;
  a7 = 0;
  if ( !Src )
    return 1;
  if ( !a4 )
    return 0;
  v16 = 0;
  if ( *(_DWORD *)(a4 + 4) == 1196442656 )
  {
    v17 = 1;
  }
  else
  {
    v17 = 0;
    if ( *(_DWORD *)(a4 + 4) != 1347437600 )
      v16 = -2147418113;
  }
  if ( v16 < 0 )
    return 0;
  if ( v17 )
    return 0;
  v18 = a9;
  v19 = PConvertToCurrentVersionDevmodeWithOemPlugins(a10, a2, (struct _RAWBINARYDATA *)a4, a4, Src, a1, a9, &a7);
  v20 = v19;
  if ( !v19 )
    return 0;
  v21 = PSBMergeDriverDevmode((__int64)a1, a2, a3, (_DWORD *)a4, a5, a6, (__int64)v19, v10);
  if ( v21 && a7 )
  {
    v22 = *((_DWORD *)v18 + 2);
    if ( !v22 )
    {
LABEL_20:
      v21 = 1;
      goto LABEL_21;
    }
    v23 = a2 + 976;
    v24 = (struct _OEM_DMEXTRAHEADER *)((char *)v20 + v23);
    v25 = (struct _OEM_DMEXTRAHEADER *)((char *)a1 + v23);
    v26 = (struct _OEM_PLUGINS *)((char *)v18 + 24);
    while ( 1 )
    {
      if ( *((_QWORD *)v26 + 4) )
      {
        if ( !(unsigned int)BCallOEMDevMode(a10, *(void **)v18, v26, 4u, a1, v20, v25, v24) )
        {
          v21 = 0;
          break;
        }
        if ( *((_DWORD *)v26 + 16) )
        {
          v27 = *((unsigned int *)v26 + 16);
          *((_QWORD *)v26 + 7) = v25;
          v25 = (struct _OEM_DMEXTRAHEADER *)((char *)v25 + v27);
          v24 = (struct _OEM_DMEXTRAHEADER *)((char *)v24 + v27);
        }
      }
      v26 = (struct _OEM_PLUGIN_ENTRY *)((char *)v26 + 176);
      if ( !--v22 )
        goto LABEL_20;
    }
  }
LABEL_21:
  LocalFree(v20);
  return v21;
}

```

## disassembly

```asm
0x180030a2c  mov     rax, rsp
0x180030a2f  push    rbp
0x180030a30  push    rsi
0x180030a31  push    rdi
0x180030a32  push    r12
0x180030a34  push    r13
0x180030a36  push    r14
0x180030a38  push    r15
0x180030a3a  sub     rsp, 40h
0x180030a3e  mov     rsi, [rsp+78h+arg_38]
0x180030a46  mov     rdi, r9
0x180030a49  mov     dword ptr [rax+38h], 0
0x180030a50  mov     r12, r8
0x180030a53  mov     r14d, edx
0x180030a56  mov     r13, rcx
0x180030a59  test    rsi, rsi
0x180030a5c  jnz     short loc_180030A66
0x180030a5e  lea     eax, [rsi+1]
0x180030a61  jmp     loc_180030BB6
0x180030a66  test    rdi, rdi
0x180030a69  jz      loc_180030BB4
0x180030a6f  xor     ecx, ecx
0x180030a71  cmp     dword ptr [r9+4], 47504420h
0x180030a79  jz      short loc_180030A8E
0x180030a7b  xor     eax, eax
0x180030a7d  cmp     dword ptr [r9+4], 50504420h
0x180030a85  jz      short loc_180030A93
0x180030a87  mov     ecx, 8000FFFFh
0x180030a8c  jmp     short loc_180030A93
0x180030a8e  mov     eax, 1
0x180030a93  test    ecx, ecx
0x180030a95  js      loc_180030BB4
0x180030a9b  test    eax, eax
0x180030a9d  jnz     loc_180030BB4
0x180030aa3  mov     r15, [rsp+78h+arg_40]
0x180030aab  lea     rax, [rsp+78h+arg_30]
0x180030ab3  mov     rcx, [rsp+78h+arg_48]; void *
0x180030abb  mov     r8, rdi; struct _RAWBINARYDATA *
0x180030abe  mov     [rsp+78h+var_40], rax; unsigned int *
0x180030ac3  mov     [rsp+78h+var_48], r15; struct _OEM_PLUGINS *
0x180030ac8  mov     [rsp+78h+var_50], r13; struct _devicemodeW *
0x180030acd  mov     [rsp+78h+Src], rsi; Src
0x180030ad2  call    ?PConvertToCurrentVersionDevmodeWithOemPlugins@@YAPEAU_devicemodeW@@PEAXKPEAU_RAWBINARYDATA@@KPEAU1@2PEAU_OEM_PLUGINS@@PEAK@Z; PConvertToCurrentVersionDevmodeWithOemPlugins(void *,ulong,_RAWBINARYDATA *,ulong,_devicemodeW *,_devicemodeW *,_OEM_PLUGINS *,ulong *)
0x180030ad7  mov     rbp, rax
0x180030ada  test    rax, rax
0x180030add  jz      loc_180030BB4
0x180030ae3  mov     rcx, [rsp+78h+arg_28]
0x180030aeb  mov     r9, rdi
0x180030aee  mov     [rsp+78h+var_40], rsi
0x180030af3  mov     r8, r12
0x180030af6  mov     [rsp+78h+var_48], rax
0x180030afb  mov     edx, r14d
0x180030afe  mov     [rsp+78h+var_50], rcx
0x180030b03  mov     rcx, [rsp+78h+arg_20]
0x180030b0b  mov     [rsp+78h+Src], rcx
0x180030b10  mov     rcx, r13
0x180030b13  call    PSBMergeDriverDevmode
0x180030b18  mov     edi, eax
0x180030b1a  test    eax, eax
0x180030b1c  jz      loc_180030BA3
0x180030b22  cmp     [rsp+78h+arg_30], 0
0x180030b2a  jz      short loc_180030BA3
0x180030b2c  mov     esi, [r15+8]
0x180030b30  test    esi, esi
0x180030b32  jz      short loc_180030B9E
0x180030b34  lea     eax, [r14+3D0h]
0x180030b3b  lea     r12, [rax+rbp]
0x180030b3f  lea     r14, [rax+r13]
0x180030b43  lea     rdi, [r15+18h]
0x180030b47  cmp     qword ptr [rdi+20h], 0
0x180030b4c  jz      short loc_180030B92
0x180030b4e  mov     rdx, [r15]; void *
0x180030b51  mov     r9d, 4; unsigned int
0x180030b57  mov     rcx, [rsp+78h+arg_48]; void *
0x180030b5f  mov     r8, rdi; struct _OEM_PLUGIN_ENTRY *
0x180030b62  mov     [rsp+78h+var_40], r12; struct _OEM_DMEXTRAHEADER *
0x180030b67  mov     [rsp+78h+var_48], r14; struct _OEM_DMEXTRAHEADER *
0x180030b6c  mov     [rsp+78h+var_50], rbp; struct _devicemodeW *
0x180030b71  mov     [rsp+78h+Src], r13; struct _devicemodeW *
0x180030b76  call    ?BCallOEMDevMode@@YAHPEAX0PEAU_OEM_PLUGIN_ENTRY@@KPEAU_devicemodeW@@2PEAU_OEM_DMEXTRAHEADER@@3@Z; BCallOEMDevMode(void *,void *,_OEM_PLUGIN_ENTRY *,ulong,_devicemodeW *,_devicemodeW *,_OEM_DMEXTRAHEADER *,_OEM_DMEXTRAHEADER *)
0x180030b7b  test    eax, eax
0x180030b7d  jz      short loc_180030BB0
0x180030b7f  cmp     dword ptr [rdi+40h], 0
0x180030b83  jz      short loc_180030B92
0x180030b85  mov     eax, [rdi+40h]
0x180030b88  mov     [rdi+38h], r14
0x180030b8c  add     r14, rax
0x180030b8f  add     r12, rax
0x180030b92  add     rdi, 0B0h
0x180030b99  add     esi, 0FFFFFFFFh
0x180030b9c  jnz     short loc_180030B47
0x180030b9e  mov     edi, 1
0x180030ba3  mov     rcx, rbp; hMem
0x180030ba6  call    cs:__imp_LocalFree
0x180030bac  mov     eax, edi
0x180030bae  jmp     short loc_180030BB6
0x180030bb0  xor     edi, edi
0x180030bb2  jmp     short loc_180030BA3
0x180030bb4  xor     eax, eax
0x180030bb6  add     rsp, 40h
0x180030bba  pop     r15
0x180030bbc  pop     r14
0x180030bbe  pop     r13
0x180030bc0  pop     r12
0x180030bc2  pop     rdi
0x180030bc3  pop     rsi
0x180030bc4  pop     rbp
0x180030bc5  retn
```
