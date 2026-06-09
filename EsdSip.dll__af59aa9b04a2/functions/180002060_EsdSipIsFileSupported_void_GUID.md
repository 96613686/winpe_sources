# EsdSipIsFileSupported(void *,_GUID *)

- ea: `0x180002060`
- end: `0x18000213b`
- name: `?EsdSipIsFileSupported@@YAHPEAXPEAU_GUID@@@Z`
- size: `219`
- prototype: `__int64 __fastcall(char *, struct _GUID *)`
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path`

## callees

- `0x180002060`
- `0x180002568`
- `0x180002a4c`
- `0x180002c08`
- `0x180003020`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180002111`
- `KERNEL32!HeapFree` at `0x180002111`
- `KERNEL32!SetLastError` at `0x180002120`
- `KERNEL32!SetLastError` at `0x180002120`
- `KERNEL32!GetProcessHeap` at `0x180002103`
- `KERNEL32!GetProcessHeap` at `0x180002103`
- `KERNEL32!GetLastError` at `0x1800020a3`
- `KERNEL32!GetLastError` at `0x1800020d8`
- `KERNEL32!GetLastError` at `0x1800020a3`
- `KERNEL32!GetLastError` at `0x1800020d8`

## pseudocode

```c
__int64 __fastcall EsdSipIsFileSupported(char *a1, struct _GUID *a2)
{
  unsigned int v2; // ebp
  const unsigned __int16 *v5; // rax
  unsigned __int16 *v6; // rdi
  DWORD LastError; // ebx
  GUID *v8; // rcx
  HANDLE ProcessHeap; // rax
  __m128i si128; // [rsp+20h] [rbp-38h] BYREF

  v2 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  if ( (unsigned __int64)(a1 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && a2 )
  {
    v5 = (const unsigned __int16 *)FormFinalPathNameByHandle(a1);
    v6 = (unsigned __int16 *)v5;
    if ( v5 )
    {
      if ( IsSupportedFileType(v5) )
      {
        si128.m128i_i64[0] = (__int64)a1;
        si128.m128i_i64[1] = (__int64)a1;
        if ( (unsigned int)IsFileObjectSupported((const struct CFile *)&si128) )
        {
          v8 = &GUID_ESDSIP;
          if ( *(_QWORD *)&g_pgSubject.Data1 )
            v8 = *(GUID **)&g_pgSubject.Data1;
          LastError = 0;
          v2 = 1;
          *a2 = *v8;
        }
        else
        {
          LastError = GetLastError();
        }
      }
      else
      {
        LastError = 1630;
      }
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v6);
    }
    else
    {
      LastError = GetLastError();
    }
  }
  else
  {
    LastError = 87;
  }
  SetLastError(LastError);
  CFile::~CFile((CFile *)&si128);
  return v2;
}

```

## disassembly

```asm
0x180002060  push    rbx
0x180002062  push    rbp
0x180002063  push    rsi
0x180002064  push    rdi
0x180002065  sub     rsp, 38h
0x180002069  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180002071  lea     rax, [rcx-1]
0x180002075  xor     ebp, ebp
0x180002077  mov     rsi, rdx
0x18000207a  mov     rbx, rcx
0x18000207d  movdqu  [rsp+58h+var_38], xmm0
0x180002083  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180002087  ja      loc_180002119
0x18000208d  test    rdx, rdx
0x180002090  jz      loc_180002119
0x180002096  call    FormFinalPathNameByHandle
0x18000209b  mov     rdi, rax
0x18000209e  test    rax, rax
0x1800020a1  jnz     short loc_1800020AD
0x1800020a3  call    cs:__imp_GetLastError
0x1800020a9  mov     ebx, eax
0x1800020ab  jmp     short loc_18000211E
0x1800020ad  mov     rcx, rdi; unsigned __int16 *
0x1800020b0  call    ?IsSupportedFileType@@YA_NPEBG@Z; IsSupportedFileType(ushort const *)
0x1800020b5  test    al, al
0x1800020b7  jnz     short loc_1800020C0
0x1800020b9  mov     ebx, 65Eh
0x1800020be  jmp     short loc_180002103
0x1800020c0  lea     rcx, [rsp+58h+var_38]; this
0x1800020c5  mov     qword ptr [rsp+58h+var_38], rbx
0x1800020ca  mov     qword ptr [rsp+58h+var_38+8], rbx
0x1800020cf  call    ?IsFileObjectSupported@@YAHAEBVCFile@@@Z; IsFileObjectSupported(CFile const &)
0x1800020d4  test    eax, eax
0x1800020d6  jnz     short loc_1800020E2
0x1800020d8  call    cs:__imp_GetLastError
0x1800020de  mov     ebx, eax
0x1800020e0  jmp     short loc_180002103
0x1800020e2  mov     rax, qword ptr cs:?g_pgSubject@@3PEAU_GUID@@EA.Data1; _GUID * g_pgSubject ...
0x1800020e9  lea     rcx, GUID_ESDSIP
0x1800020f0  test    rax, rax
0x1800020f3  cmovnz  rcx, rax
0x1800020f7  xor     ebx, ebx
0x1800020f9  movups  xmm0, xmmword ptr [rcx]
0x1800020fc  lea     ebp, [rbx+1]
0x1800020ff  movdqu  xmmword ptr [rsi], xmm0
0x180002103  call    cs:__imp_GetProcessHeap
0x180002109  mov     r8, rdi; lpMem
0x18000210c  xor     edx, edx; dwFlags
0x18000210e  mov     rcx, rax; hHeap
0x180002111  call    cs:__imp_HeapFree
0x180002117  jmp     short loc_18000211E
0x180002119  mov     ebx, 57h ; 'W'
0x18000211e  mov     ecx, ebx; dwErrCode
0x180002120  call    cs:__imp_SetLastError
0x180002126  lea     rcx, [rsp+58h+var_38]; this
0x18000212b  call    ??1CFile@@QEAA@XZ; CFile::~CFile(void)
0x180002130  mov     eax, ebp
0x180002132  add     rsp, 38h
0x180002136  pop     rdi
0x180002137  pop     rsi
0x180002138  pop     rbp
0x180002139  pop     rbx
0x18000213a  retn
```
