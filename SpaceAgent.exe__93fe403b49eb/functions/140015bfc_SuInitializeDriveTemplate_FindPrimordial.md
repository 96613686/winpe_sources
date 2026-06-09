# SuInitializeDriveTemplate_FindPrimordial

- ea: `0x140015bfc`
- end: `0x140015e07`
- name: `SuInitializeDriveTemplate_FindPrimordial`
- size: `523`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140015a98`

## callees

- `0x140001caf`
- `0x1400083dc`
- `0x140008454`
- `0x14000df58`
- `0x140015890`
- `0x140015bfc`
- `0x14001b830`
- `0x14001c8a0`
- `0x14001ed92`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140015c92`
- `KERNEL32!LocalFree` at `0x140015d8d`
- `KERNEL32!LocalFree` at `0x140015db1`
- `KERNEL32!LocalFree` at `0x140015c92`
- `KERNEL32!LocalFree` at `0x140015d8d`
- `KERNEL32!LocalFree` at `0x140015db1`
- `KERNEL32!SetLastError` at `0x140015ccf`
- `KERNEL32!SetLastError` at `0x140015deb`
- `KERNEL32!SetLastError` at `0x140015ccf`
- `KERNEL32!SetLastError` at `0x140015deb`
- `KERNEL32!GetLastError` at `0x140015d20`
- `KERNEL32!GetLastError` at `0x140015d2c`
- `KERNEL32!GetLastError` at `0x140015da1`
- `KERNEL32!GetLastError` at `0x140015dc5`
- `KERNEL32!GetLastError` at `0x140015de1`
- `KERNEL32!GetLastError` at `0x140015d20`
- `KERNEL32!GetLastError` at `0x140015d2c`
- `KERNEL32!GetLastError` at `0x140015da1`
- `KERNEL32!GetLastError` at `0x140015dc5`
- `KERNEL32!GetLastError` at `0x140015de1`

## pseudocode

```c
__int64 __fastcall SuInitializeDriveTemplate_FindPrimordial(int a1, int a2, _DWORD *a3)
{
  WCHAR *v6; // r14
  __int64 *FirstDrive; // r12
  unsigned int Next; // ebx
  unsigned __int16 *v9; // rdi
  HLOCAL v10; // rax
  unsigned int DrivePath; // eax
  const struct _GUID *v12; // rdx
  DWORD LastError; // esi
  HLOCAL v14; // rax
  HLOCAL v15; // rax
  unsigned int Close; // eax
  PCWSTR DevicePath; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int64 v19; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE Src[40]; // [rsp+30h] [rbp-D0h] BYREF
  GUID v21; // [rsp+58h] [rbp-A8h]
  HLOCAL hMem; // [rsp+CC8h] [rbp+BC8h] BYREF

  memset_0(Src, 0, 0xB48u);
  v6 = 0;
  hMem = 0;
  DevicePath = 0;
  v19 = 256;
  v21 = GUID_NULL;
  FirstDrive = (__int64 *)SuFindFirstDrive((struct _SU_POOL_OBJECT *)Src, (struct _SU_DRIVE_OBJECT **)&hMem);
  if ( FirstDrive == (__int64 *)-1LL )
  {
    Next = 0;
LABEL_3:
    v9 = (unsigned __int16 *)hMem;
  }
  else
  {
    while ( 1 )
    {
      v9 = (unsigned __int16 *)hMem;
      if ( *((_DWORD *)hMem + 28) == a1 )
        break;
      v10 = LocalFree(hMem);
      v9 = 0;
      hMem = 0;
      if ( v10 )
      {
        Next = 0;
        goto LABEL_16;
      }
      Next = SuFindNext(FirstDrive, (struct _SU_OBJECT **)&hMem);
      if ( !Next )
        goto LABEL_3;
    }
    if ( *((_DWORD *)hMem + 19) >= 0xC30u )
    {
      DrivePath = SuGetDrivePath((struct _SU_DRIVE_OBJECT *)hMem, (unsigned __int16 **)&DevicePath);
      v6 = (WCHAR *)DevicePath;
      Next = DrivePath;
      if ( DrivePath )
      {
        if ( !a2 || (Next = PartitionDisk(DevicePath, 1)) != 0 )
        {
          Next = GetDeviceNameByInterface(v6, v12, &v19, v9 + 60);
          if ( !Next )
            Next = GetLastError() == 122;
        }
      }
    }
    else
    {
      Next = 0;
      SetLastError(0xDu);
    }
  }
LABEL_16:
  LastError = GetLastError();
  if ( LastError == 18 )
    LastError = 2;
  if ( Next )
  {
    memcpy_0(a3, v9 + 36, 0xC30u);
    a3[1] = 3120;
    a3[742] = 0;
  }
  else
  {
    memset_0(Src, 0, 0xC30u);
    memcpy_0(a3, Src, 0xC30u);
  }
  if ( v6 )
  {
    v14 = LocalFree(v6);
    if ( Next )
    {
      Next = v14 == 0;
      LastError = GetLastError();
    }
  }
  if ( v9 )
  {
    v15 = LocalFree(v9);
    if ( Next )
    {
      Next = v15 == 0;
      LastError = GetLastError();
    }
  }
  if ( FirstDrive != (__int64 *)-1LL )
  {
    Close = SuFindClose((char *)FirstDrive);
    if ( Next )
    {
      Next = Close;
      LastError = GetLastError();
    }
  }
  SetLastError(LastError);
  return Next;
}

```

## disassembly

```asm
0x140015bfc  push    rbp
0x140015bfe  push    rbx
0x140015bff  push    rsi
0x140015c00  push    rdi
0x140015c01  push    r12
0x140015c03  push    r13
0x140015c05  push    r14
0x140015c07  push    r15
0x140015c09  lea     rbp, [rsp-0B68h]
0x140015c11  sub     rsp, 0C68h
0x140015c18  mov     r15, r8
0x140015c1b  mov     r13d, edx
0x140015c1e  mov     esi, ecx
0x140015c20  xor     edx, edx; Val
0x140015c22  mov     r8d, 0B48h; Size
0x140015c28  lea     rcx, [rsp+0CA0h+Src]; void *
0x140015c2d  call    memset_0
0x140015c32  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140015c39  xor     r14d, r14d
0x140015c3c  mov     [rbp+0BA0h+hMem], 0
0x140015c47  lea     rdx, [rbp+0BA0h+hMem]; struct _SU_DRIVE_OBJECT **
0x140015c4e  mov     [rsp+0CA0h+DevicePath], r14
0x140015c53  lea     rcx, [rsp+0CA0h+Src]; struct _SU_POOL_OBJECT *
0x140015c58  mov     [rsp+0CA0h+var_C78], 100h
0x140015c61  movdqu  [rsp+0CA0h+var_C48], xmm0
0x140015c67  call    ?SuFindFirstDrive@@YAPEAXPEAU_SU_POOL_OBJECT@@PEAPEAU_SU_DRIVE_OBJECT@@@Z; SuFindFirstDrive(_SU_POOL_OBJECT *,_SU_DRIVE_OBJECT * *)
0x140015c6c  mov     r12, rax
0x140015c6f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140015c73  jnz     short loc_140015C83
0x140015c75  xor     ebx, ebx
0x140015c77  mov     rdi, [rbp+0BA0h+hMem]
0x140015c7e  jmp     loc_140015D2C
0x140015c83  mov     rdi, [rbp+0BA0h+hMem]
0x140015c8a  cmp     [rdi+70h], esi
0x140015c8d  jz      short loc_140015CC1
0x140015c8f  mov     rcx, rdi; hMem
0x140015c92  call    cs:__imp_LocalFree
0x140015c98  xor     edi, edi
0x140015c9a  mov     [rbp+0BA0h+hMem], rdi
0x140015ca1  test    rax, rax
0x140015ca4  jnz     short loc_140015CBD
0x140015ca6  lea     rdx, [rbp+0BA0h+hMem]; struct _SU_OBJECT **
0x140015cad  mov     rcx, r12; void *
0x140015cb0  call    ?SuFindNext@@YAHPEAXPEAPEAU_SU_OBJECT@@@Z; SuFindNext(void *,_SU_OBJECT * *)
0x140015cb5  mov     ebx, eax
0x140015cb7  test    eax, eax
0x140015cb9  jnz     short loc_140015C83
0x140015cbb  jmp     short loc_140015C77
0x140015cbd  xor     ebx, ebx
0x140015cbf  jmp     short loc_140015D2C
0x140015cc1  cmp     dword ptr [rdi+4Ch], 0C30h
0x140015cc8  jnb     short loc_140015CD7
0x140015cca  xor     ebx, ebx
0x140015ccc  lea     ecx, [rbx+0Dh]; dwErrCode
0x140015ccf  call    cs:__imp_SetLastError
0x140015cd5  jmp     short loc_140015D2C
0x140015cd7  lea     rdx, [rsp+0CA0h+DevicePath]; unsigned __int16 **
0x140015cdc  mov     rcx, rdi; struct _SU_DRIVE_OBJECT *
0x140015cdf  call    ?SuGetDrivePath@@YAHPEAU_SU_DRIVE_OBJECT@@PEAPEAG@Z; SuGetDrivePath(_SU_DRIVE_OBJECT *,ushort * *)
0x140015ce4  mov     r14, [rsp+0CA0h+DevicePath]
0x140015ce9  mov     ebx, eax
0x140015ceb  test    eax, eax
0x140015ced  jz      short loc_140015D2C
0x140015cef  mov     esi, 1
0x140015cf4  test    r13d, r13d
0x140015cf7  jz      short loc_140015D09
0x140015cf9  mov     edx, esi; int
0x140015cfb  mov     rcx, r14; unsigned __int16 *
0x140015cfe  call    ?PartitionDisk@@YAHPEBGHH@Z; PartitionDisk(ushort const *,int,int)
0x140015d03  mov     ebx, eax
0x140015d05  test    eax, eax
0x140015d07  jz      short loc_140015D2C
0x140015d09  lea     r9, [rdi+78h]; unsigned __int16 *
0x140015d0d  mov     rcx, r14; DevicePath
0x140015d10  lea     r8, [rsp+0CA0h+var_C78]; unsigned __int64 *
0x140015d15  call    ?GetDeviceNameByInterface@@YAHPEBGPEBU_GUID@@PEA_KPEAG@Z; GetDeviceNameByInterface(ushort const *,_GUID const *,unsigned __int64 *,ushort *)
0x140015d1a  mov     ebx, eax
0x140015d1c  test    eax, eax
0x140015d1e  jnz     short loc_140015D2C
0x140015d20  call    cs:__imp_GetLastError
0x140015d26  cmp     eax, 7Ah ; 'z'
0x140015d29  cmovz   ebx, esi
0x140015d2c  call    cs:__imp_GetLastError
0x140015d32  mov     esi, eax
0x140015d34  mov     r13d, 0C30h
0x140015d3a  cmp     esi, 12h
0x140015d3d  mov     eax, 2
0x140015d42  mov     r8d, r13d; Size
0x140015d45  cmovz   esi, eax
0x140015d48  test    ebx, ebx
0x140015d4a  jnz     short loc_140015D6A
0x140015d4c  xor     edx, edx; Val
0x140015d4e  lea     rcx, [rsp+0CA0h+Src]; void *
0x140015d53  call    memset_0
0x140015d58  mov     rcx, r15; void *
0x140015d5b  lea     rdx, [rsp+0CA0h+Src]; Src
0x140015d60  mov     r8d, r13d; Size
0x140015d63  call    memcpy_0
0x140015d68  jmp     short loc_140015D85
0x140015d6a  mov     rcx, r15; void *
0x140015d6d  lea     rdx, [rdi+48h]; Src
0x140015d71  call    memcpy_0
0x140015d76  mov     [r15+4], r13d
0x140015d7a  mov     dword ptr [r15+0B98h], 0
0x140015d85  test    r14, r14
0x140015d88  jz      short loc_140015DA9
0x140015d8a  mov     rcx, r14; hMem
0x140015d8d  call    cs:__imp_LocalFree
0x140015d93  xor     ecx, ecx
0x140015d95  test    rax, rax
0x140015d98  setz    cl
0x140015d9b  test    ebx, ebx
0x140015d9d  jz      short loc_140015DA9
0x140015d9f  mov     ebx, ecx
0x140015da1  call    cs:__imp_GetLastError
0x140015da7  mov     esi, eax
0x140015da9  test    rdi, rdi
0x140015dac  jz      short loc_140015DCD
0x140015dae  mov     rcx, rdi; hMem
0x140015db1  call    cs:__imp_LocalFree
0x140015db7  xor     ecx, ecx
0x140015db9  test    rax, rax
0x140015dbc  setz    cl
0x140015dbf  test    ebx, ebx
0x140015dc1  jz      short loc_140015DCD
0x140015dc3  mov     ebx, ecx
0x140015dc5  call    cs:__imp_GetLastError
0x140015dcb  mov     esi, eax
0x140015dcd  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x140015dd1  jz      short loc_140015DE9
0x140015dd3  mov     rcx, r12; hMem
0x140015dd6  call    ?SuFindClose@@YAHPEAX@Z; SuFindClose(void *)
0x140015ddb  test    ebx, ebx
0x140015ddd  jz      short loc_140015DE9
0x140015ddf  mov     ebx, eax
0x140015de1  call    cs:__imp_GetLastError
0x140015de7  mov     esi, eax
0x140015de9  mov     ecx, esi; dwErrCode
0x140015deb  call    cs:__imp_SetLastError
0x140015df1  mov     eax, ebx
0x140015df3  add     rsp, 0C68h
0x140015dfa  pop     r15
0x140015dfc  pop     r14
0x140015dfe  pop     r13
0x140015e00  pop     r12
0x140015e02  pop     rdi
0x140015e03  pop     rsi
0x140015e04  pop     rbx
0x140015e05  pop     rbp
0x140015e06  retn
```
