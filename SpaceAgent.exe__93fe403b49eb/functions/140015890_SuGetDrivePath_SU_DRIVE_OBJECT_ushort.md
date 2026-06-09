# SuGetDrivePath(_SU_DRIVE_OBJECT *,ushort * *)

- ea: `0x140015890`
- end: `0x140015933`
- name: `?SuGetDrivePath@@YAHPEAU_SU_DRIVE_OBJECT@@PEAPEAG@Z`
- size: `163`
- prototype: `__int64 __fastcall(struct _SU_DRIVE_OBJECT *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140015bfc`

## callees

- `0x14000a440`
- `0x14001480c`
- `0x140015890`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1400158f8`
- `KERNEL32!LocalFree` at `0x14001590a`
- `KERNEL32!LocalFree` at `0x1400158f8`
- `KERNEL32!LocalFree` at `0x14001590a`
- `KERNEL32!SetLastError` at `0x14001591e`
- `KERNEL32!SetLastError` at `0x14001591e`
- `KERNEL32!GetLastError` at `0x1400158e6`
- `KERNEL32!GetLastError` at `0x1400158e6`

## pseudocode

```c
__int64 __fastcall SuGetDrivePath(struct _SU_DRIVE_OBJECT *a1, unsigned __int16 **a2)
{
  unsigned __int16 *v4; // rbx
  unsigned int Pool; // edi
  unsigned int DiskPath; // eax
  DWORD LastError; // ebp
  unsigned __int16 *v9; // [rsp+50h] [rbp+18h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp+20h] BYREF

  v4 = 0;
  v9 = 0;
  hMem = 0;
  Pool = SiGetPool(&GUID_NULL, 0, (struct _SU_POOL_OBJECT **)&hMem);
  if ( Pool )
  {
    DiskPath = SuGetDiskPath(*((_DWORD *)a1 + 28), *((_DWORD *)a1 + 710) == 2, &v9);
    v4 = v9;
    Pool = DiskPath;
  }
  LastError = GetLastError();
  if ( hMem )
    LocalFree(hMem);
  if ( Pool )
  {
    *a2 = v4;
  }
  else
  {
    if ( v4 )
      LocalFree(v4);
    *a2 = 0;
  }
  SetLastError(LastError);
  return Pool;
}

```

## disassembly

```asm
0x140015890  mov     rax, rsp
0x140015893  mov     [rax+8], rbx
0x140015897  push    rbp
0x140015898  push    rsi
0x140015899  push    rdi
0x14001589a  sub     rsp, 20h
0x14001589e  mov     rsi, rdx
0x1400158a1  lea     r8, [rax+20h]; struct _SU_POOL_OBJECT **
0x1400158a5  mov     rbp, rcx
0x1400158a8  xor     ebx, ebx
0x1400158aa  xor     edx, edx; unsigned int
0x1400158ac  mov     [rax+18h], rbx
0x1400158b0  lea     rcx, GUID_NULL; struct _GUID *
0x1400158b7  mov     [rax+20h], rbx
0x1400158bb  call    ?SiGetPool@@YAHPEAU_GUID@@KPEAPEAU_SU_POOL_OBJECT@@@Z; SiGetPool(_GUID *,ulong,_SU_POOL_OBJECT * *)
0x1400158c0  mov     edi, eax
0x1400158c2  test    eax, eax
0x1400158c4  jz      short loc_1400158E6
0x1400158c6  mov     ecx, [rbp+70h]; unsigned int
0x1400158c9  lea     r8, [rsp+38h+arg_10]; unsigned __int16 **
0x1400158ce  xor     edx, edx
0x1400158d0  cmp     dword ptr [rbp+0B18h], 2
0x1400158d7  setz    dl; int
0x1400158da  call    ?SuGetDiskPath@@YAHKHPEAPEAG@Z; SuGetDiskPath(ulong,int,ushort * *)
0x1400158df  mov     rbx, [rsp+38h+arg_10]
0x1400158e4  mov     edi, eax
0x1400158e6  call    cs:__imp_GetLastError
0x1400158ec  mov     rcx, [rsp+38h+hMem]; hMem
0x1400158f1  mov     ebp, eax
0x1400158f3  test    rcx, rcx
0x1400158f6  jz      short loc_1400158FE
0x1400158f8  call    cs:__imp_LocalFree
0x1400158fe  test    edi, edi
0x140015900  jnz     short loc_140015919
0x140015902  test    rbx, rbx
0x140015905  jz      short loc_140015910
0x140015907  mov     rcx, rbx; hMem
0x14001590a  call    cs:__imp_LocalFree
0x140015910  mov     qword ptr [rsi], 0
0x140015917  jmp     short loc_14001591C
0x140015919  mov     [rsi], rbx
0x14001591c  mov     ecx, ebp; dwErrCode
0x14001591e  call    cs:__imp_SetLastError
0x140015924  mov     rbx, [rsp+38h+arg_0]
0x140015929  mov     eax, edi
0x14001592b  add     rsp, 20h
0x14001592f  pop     rdi
0x140015930  pop     rsi
0x140015931  pop     rbp
0x140015932  retn
```
