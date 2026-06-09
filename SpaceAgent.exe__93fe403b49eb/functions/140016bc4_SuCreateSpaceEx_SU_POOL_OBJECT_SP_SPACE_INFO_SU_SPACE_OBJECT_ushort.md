# SuCreateSpaceEx(_SU_POOL_OBJECT *,_SP_SPACE_INFO *,_SU_SPACE_OBJECT * *,ushort * *)

- ea: `0x140016bc4`
- end: `0x140016ca7`
- name: `?SuCreateSpaceEx@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SP_SPACE_INFO@@PEAPEAU_SU_SPACE_OBJECT@@PEAPEAG@Z`
- size: `227`
- prototype: `__int64 __fastcall(struct _SU_POOL_OBJECT *, struct _SP_SPACE_INFO *, struct _SU_SPACE_OBJECT **, struct _SP_TIER_INFO **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140018a8c`

## callees

- `0x140012704`
- `0x14001480c`
- `0x1400166f8`
- `0x140016bc4`
- `0x140016cb0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140016c3d`
- `KERNEL32!LocalFree` at `0x140016c5d`
- `KERNEL32!LocalFree` at `0x140016c3d`
- `KERNEL32!LocalFree` at `0x140016c5d`
- `KERNEL32!SetLastError` at `0x140016c71`
- `KERNEL32!SetLastError` at `0x140016c90`
- `KERNEL32!SetLastError` at `0x140016c71`
- `KERNEL32!SetLastError` at `0x140016c90`
- `KERNEL32!GetLastError` at `0x140016c28`
- `KERNEL32!GetLastError` at `0x140016c52`
- `KERNEL32!GetLastError` at `0x140016c67`
- `KERNEL32!GetLastError` at `0x140016c28`
- `KERNEL32!GetLastError` at `0x140016c52`
- `KERNEL32!GetLastError` at `0x140016c67`

## pseudocode

```c
__int64 __fastcall SuCreateSpaceEx(
        struct _SU_POOL_OBJECT *a1,
        struct _SP_SPACE_INFO *a2,
        struct _SU_SPACE_OBJECT **a3,
        struct _SP_TIER_INFO **a4)
{
  unsigned __int16 *v4; // rbx
  unsigned int Space; // eax
  struct _SU_SPACE_OBJECT *v8; // rdi
  unsigned int v9; // esi
  unsigned int DiskPath; // eax
  DWORD LastError; // r12d
  int v12; // ebx
  DWORD v13; // ebp
  HLOCAL hMem; // [rsp+30h] [rbp-48h] BYREF
  unsigned __int16 *v16; // [rsp+38h] [rbp-40h] BYREF

  hMem = 0;
  v4 = 0;
  v16 = 0;
  Space = SuCreateSpace(a1, a2, (__int64)a3, a4, (struct _SU_SPACE_OBJECT **)&hMem);
  v8 = (struct _SU_SPACE_OBJECT *)hMem;
  v9 = Space;
  if ( Space )
  {
    v9 = SuAttachSpaceEx((struct _SU_SPACE_OBJECT *)hMem);
    if ( v9 )
    {
      DiskPath = SuGetDiskPath(*((_DWORD *)v8 + 669), 0, &v16);
      v4 = v16;
      v9 = DiskPath;
    }
  }
  LastError = GetLastError();
  if ( v9 )
  {
    *a3 = v8;
    *a4 = (struct _SP_TIER_INFO *)v4;
  }
  else
  {
    if ( v4 )
      LocalFree(v4);
    if ( v8 )
    {
      v12 = SuDeleteSpaceEx(v8);
      v13 = GetLastError();
      LocalFree(v8);
      if ( v12 )
        v13 = GetLastError();
      SetLastError(v13);
    }
    *a3 = 0;
    *a4 = 0;
  }
  SetLastError(LastError);
  return v9;
}

```

## disassembly

```asm
0x140016bc4  mov     r11, rsp
0x140016bc7  push    rbx
0x140016bc8  push    rbp
0x140016bc9  push    rsi
0x140016bca  push    rdi
0x140016bcb  push    r12
0x140016bcd  push    r14
0x140016bcf  push    r15
0x140016bd1  sub     rsp, 40h
0x140016bd5  lea     rax, [r11-48h]
0x140016bd9  mov     qword ptr [r11-48h], 0
0x140016be1  xor     ebx, ebx
0x140016be3  mov     [r11-58h], rax
0x140016be7  mov     [r11-40h], rbx
0x140016beb  mov     r14, r9
0x140016bee  mov     r15, r8
0x140016bf1  call    ?SuCreateSpace@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SP_SPACE_INFO@@KQEAPEAU_SP_TIER_INFO@@PEAPEAU_SU_SPACE_OBJECT@@@Z; SuCreateSpace(_SU_POOL_OBJECT *,_SP_SPACE_INFO *,ulong,_SP_TIER_INFO * * const,_SU_SPACE_OBJECT * *)
0x140016bf6  mov     rdi, [rsp+78h+hMem]
0x140016bfb  mov     esi, eax
0x140016bfd  test    eax, eax
0x140016bff  jz      short loc_140016C28
0x140016c01  mov     rcx, rdi; struct _SU_SPACE_OBJECT *
0x140016c04  call    ?SuAttachSpaceEx@@YAHPEAU_SU_SPACE_OBJECT@@@Z; SuAttachSpaceEx(_SU_SPACE_OBJECT *)
0x140016c09  mov     esi, eax
0x140016c0b  test    eax, eax
0x140016c0d  jz      short loc_140016C28
0x140016c0f  mov     ecx, [rdi+0A74h]; unsigned int
0x140016c15  lea     r8, [rsp+78h+var_40]; unsigned __int16 **
0x140016c1a  xor     edx, edx; int
0x140016c1c  call    ?SuGetDiskPath@@YAHKHPEAPEAG@Z; SuGetDiskPath(ulong,int,ushort * *)
0x140016c21  mov     rbx, [rsp+78h+var_40]
0x140016c26  mov     esi, eax
0x140016c28  call    cs:__imp_GetLastError
0x140016c2e  mov     r12d, eax
0x140016c31  test    esi, esi
0x140016c33  jnz     short loc_140016C87
0x140016c35  test    rbx, rbx
0x140016c38  jz      short loc_140016C43
0x140016c3a  mov     rcx, rbx; hMem
0x140016c3d  call    cs:__imp_LocalFree
0x140016c43  test    rdi, rdi
0x140016c46  jz      short loc_140016C77
0x140016c48  mov     rcx, rdi; struct _SU_SPACE_OBJECT *
0x140016c4b  call    ?SuDeleteSpaceEx@@YAHPEAU_SU_SPACE_OBJECT@@@Z; SuDeleteSpaceEx(_SU_SPACE_OBJECT *)
0x140016c50  mov     ebx, eax
0x140016c52  call    cs:__imp_GetLastError
0x140016c58  mov     rcx, rdi; hMem
0x140016c5b  mov     ebp, eax
0x140016c5d  call    cs:__imp_LocalFree
0x140016c63  test    ebx, ebx
0x140016c65  jz      short loc_140016C6F
0x140016c67  call    cs:__imp_GetLastError
0x140016c6d  mov     ebp, eax
0x140016c6f  mov     ecx, ebp; dwErrCode
0x140016c71  call    cs:__imp_SetLastError
0x140016c77  mov     qword ptr [r15], 0
0x140016c7e  mov     qword ptr [r14], 0
0x140016c85  jmp     short loc_140016C8D
0x140016c87  mov     [r15], rdi
0x140016c8a  mov     [r14], rbx
0x140016c8d  mov     ecx, r12d; dwErrCode
0x140016c90  call    cs:__imp_SetLastError
0x140016c96  mov     eax, esi
0x140016c98  add     rsp, 40h
0x140016c9c  pop     r15
0x140016c9e  pop     r14
0x140016ca0  pop     r12
0x140016ca2  pop     rdi
0x140016ca3  pop     rsi
0x140016ca4  pop     rbp
0x140016ca5  pop     rbx
0x140016ca6  retn
```
