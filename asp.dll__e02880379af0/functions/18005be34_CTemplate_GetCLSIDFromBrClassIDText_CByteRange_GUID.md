# CTemplate::GetCLSIDFromBrClassIDText(CByteRange &,_GUID *)

- ea: `0x18005be34`
- end: `0x18005bfb4`
- name: `?GetCLSIDFromBrClassIDText@CTemplate@@AEAAXAEAVCByteRange@@PEAU_GUID@@@Z`
- size: `384`
- prototype: `void __fastcall(CTemplate *__hidden this, struct CByteRange *, LPCLSID pclsid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005eec8`

## callees

- `0x180015ee4`
- `0x18005be34`
- `0x18005ffac`

## import_xrefs

- `msvcrt!_strnicmp` at `0x18005be5c`
- `msvcrt!_strnicmp` at `0x18005be5c`
- `ole32!CLSIDFromString` at `0x18005bf52`
- `ole32!CLSIDFromString` at `0x18005bf52`
- `KERNEL32!HeapFree` at `0x18005bf1b`
- `KERNEL32!HeapFree` at `0x18005bf6d`
- `KERNEL32!HeapFree` at `0x18005bfa1`
- `KERNEL32!HeapFree` at `0x18005bf1b`
- `KERNEL32!HeapFree` at `0x18005bf6d`
- `KERNEL32!HeapFree` at `0x18005bfa1`
- `KERNEL32!HeapAlloc` at `0x18005bec4`
- `KERNEL32!HeapAlloc` at `0x18005bec4`
- `KERNEL32!RaiseException` at `0x18005bedf`
- `KERNEL32!RaiseException` at `0x18005bf30`
- `KERNEL32!RaiseException` at `0x18005bedf`
- `KERNEL32!RaiseException` at `0x18005bf30`
- `KERNEL32!MultiByteToWideChar` at `0x18005bf05`
- `KERNEL32!MultiByteToWideChar` at `0x18005bf05`

## string_xrefs

- `0x18005be4a`: `clsid:`

## pseudocode

```c
void __fastcall CTemplate::GetCLSIDFromBrClassIDText(CTemplate *this, struct CByteRange *a2, LPCLSID pclsid)
{
  __int64 v6; // rcx
  SIZE_T v7; // rax
  WCHAR *v8; // rdi

  if ( !_strnicmp(*(const char **)a2, "clsid:", 6u) )
    CByteRange::Advance(a2, 6u);
  if ( **(_BYTE **)a2 == 123 )
    CByteRange::Advance(a2, 1u);
  v6 = *((unsigned int *)a2 + 2);
  if ( *(_BYTE *)(v6 + *(_QWORD *)a2 - 1) == 125 )
  {
    LODWORD(v6) = v6 - 1;
    *((_DWORD *)a2 + 2) = v6;
  }
  v7 = 2LL * (unsigned int)(v6 + 3);
  if ( !is_mul_ok((unsigned int)(v6 + 3), 2u) )
    v7 = -1;
  v8 = (WCHAR *)HeapAlloc(g_hDenaliHeap, 0, v7);
  if ( !v8 )
    RaiseException(0x8007000E, 0, 0, 0);
  *v8 = 123;
  if ( !MultiByteToWideChar(0, 8u, *(LPCCH *)a2, *((_DWORD *)a2 + 2), v8 + 1, *((_DWORD *)a2 + 2)) )
  {
    HeapFree(g_hDenaliHeap, 0, v8);
    v8 = 0;
    RaiseException(0x80004005, 0, 0, 0);
  }
  v8[*((_DWORD *)a2 + 2) + 1] = 125;
  v8[*((_DWORD *)a2 + 2) + 2] = 0;
  if ( CLSIDFromString(v8, pclsid) >= 0 )
  {
    if ( v8 )
      HeapFree(g_hDenaliHeap, 0, v8);
  }
  else
  {
    if ( v8 )
      HeapFree(g_hDenaliHeap, 0, v8);
    CTemplate::ThrowErrorSingleInsert(
      this,
      *(unsigned __int8 **)a2,
      0x7E3u,
      *(unsigned __int8 **)a2,
      *((_DWORD *)a2 + 2));
  }
}

```

## disassembly

```asm
0x18005be34  push    rbx
0x18005be36  push    rbp
0x18005be37  push    rsi
0x18005be38  push    rdi
0x18005be39  push    r14
0x18005be3b  push    r15
0x18005be3d  sub     rsp, 38h
0x18005be41  mov     rbx, rdx
0x18005be44  mov     rbp, r8
0x18005be47  mov     rsi, rcx
0x18005be4a  lea     rdx, aClsid; "clsid:"
0x18005be51  mov     edi, 6
0x18005be56  mov     r8d, edi; MaxCount
0x18005be59  mov     rcx, [rbx]; String1
0x18005be5c  call    cs:__imp__strnicmp
0x18005be62  test    eax, eax
0x18005be64  jnz     short loc_18005BE70
0x18005be66  mov     edx, edi; unsigned int
0x18005be68  mov     rcx, rbx; this
0x18005be6b  call    ?Advance@CByteRange@@QEAAXI@Z; CByteRange::Advance(uint)
0x18005be70  mov     rax, [rbx]
0x18005be73  mov     r14d, 7Bh ; '{'
0x18005be79  cmp     [rax], r14b
0x18005be7c  jnz     short loc_18005BE8A
0x18005be7e  lea     edx, [r14-7Ah]; unsigned int
0x18005be82  mov     rcx, rbx; this
0x18005be85  call    ?Advance@CByteRange@@QEAAXI@Z; CByteRange::Advance(uint)
0x18005be8a  mov     ecx, [rbx+8]
0x18005be8d  mov     r15d, 7Dh ; '}'
0x18005be93  mov     rax, [rbx]
0x18005be96  cmp     [rcx+rax-1], r15b
0x18005be9b  jnz     short loc_18005BEA2
0x18005be9d  dec     ecx
0x18005be9f  mov     [rbx+8], ecx
0x18005bea2  add     ecx, 3
0x18005bea5  mov     eax, 2
0x18005beaa  mul     rcx
0x18005bead  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18005beb4  cmovb   rax, rcx
0x18005beb8  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x18005bebf  mov     r8, rax; dwBytes
0x18005bec2  xor     edx, edx; dwFlags
0x18005bec4  call    cs:__imp_HeapAlloc
0x18005beca  mov     rdi, rax
0x18005becd  test    rax, rax
0x18005bed0  jnz     short loc_18005BEE5
0x18005bed2  xor     r9d, r9d; lpArguments
0x18005bed5  xor     r8d, r8d; nNumberOfArguments
0x18005bed8  xor     edx, edx; dwExceptionFlags
0x18005beda  mov     ecx, 8007000Eh; dwExceptionCode
0x18005bedf  call    cs:__imp_RaiseException
0x18005bee5  mov     [rdi], r14w
0x18005bee9  lea     rcx, [rdi+2]
0x18005beed  mov     r9d, [rbx+8]; cbMultiByte
0x18005bef1  mov     edx, 8; dwFlags
0x18005bef6  mov     r8, [rbx]; lpMultiByteStr
0x18005bef9  mov     [rsp+68h+cchWideChar], r9d; cchWideChar
0x18005befe  mov     [rsp+68h+lpWideCharStr], rcx; lpWideCharStr
0x18005bf03  xor     ecx, ecx; CodePage
0x18005bf05  call    cs:__imp_MultiByteToWideChar
0x18005bf0b  test    eax, eax
0x18005bf0d  jnz     short loc_18005BF36
0x18005bf0f  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x18005bf16  mov     r8, rdi; lpMem
0x18005bf19  xor     edx, edx; dwFlags
0x18005bf1b  call    cs:__imp_HeapFree
0x18005bf21  xor     r9d, r9d; lpArguments
0x18005bf24  xor     r8d, r8d; nNumberOfArguments
0x18005bf27  xor     edx, edx; dwExceptionFlags
0x18005bf29  mov     ecx, 80004005h; dwExceptionCode
0x18005bf2e  xor     edi, edi
0x18005bf30  call    cs:__imp_RaiseException
0x18005bf36  mov     eax, [rbx+8]
0x18005bf39  mov     rdx, rbp; pclsid
0x18005bf3c  inc     eax
0x18005bf3e  mov     [rdi+rax*2], r15w
0x18005bf43  xor     eax, eax
0x18005bf45  mov     ecx, [rbx+8]
0x18005bf48  add     ecx, 2
0x18005bf4b  mov     [rdi+rcx*2], ax
0x18005bf4f  mov     rcx, rdi; lpsz
0x18005bf52  call    cs:__imp_CLSIDFromString
0x18005bf58  test    eax, eax
0x18005bf5a  jns     short loc_18005BF90
0x18005bf5c  test    rdi, rdi
0x18005bf5f  jz      short loc_18005BF73
0x18005bf61  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x18005bf68  mov     r8, rdi; lpMem
0x18005bf6b  xor     edx, edx; dwFlags
0x18005bf6d  call    cs:__imp_HeapFree
0x18005bf73  mov     r9, [rbx]; unsigned __int8 *
0x18005bf76  mov     r8d, 7E3h; unsigned int
0x18005bf7c  mov     eax, [rbx+8]
0x18005bf7f  mov     rdx, r9; unsigned __int8 *
0x18005bf82  mov     rcx, rsi; this
0x18005bf85  mov     dword ptr [rsp+68h+lpWideCharStr], eax; unsigned int
0x18005bf89  call    ?ThrowErrorSingleInsert@CTemplate@@AEAAXPEAEI0I@Z; CTemplate::ThrowErrorSingleInsert(uchar *,uint,uchar *,uint)
0x18005bf8e  jmp     short loc_18005BFA7
0x18005bf90  test    rdi, rdi
0x18005bf93  jz      short loc_18005BFA7
0x18005bf95  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x18005bf9c  mov     r8, rdi; lpMem
0x18005bf9f  xor     edx, edx; dwFlags
0x18005bfa1  call    cs:__imp_HeapFree
0x18005bfa7  add     rsp, 38h
0x18005bfab  pop     r15
0x18005bfad  pop     r14
0x18005bfaf  pop     rdi
0x18005bfb0  pop     rsi
0x18005bfb1  pop     rbp
0x18005bfb2  pop     rbx
0x18005bfb3  retn
```
