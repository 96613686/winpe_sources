# AddScaleFactors(void *,ApplicabilityContext *)

- ea: `0x180009984`
- end: `0x180009a7f`
- name: `?AddScaleFactors@@YAXPEAXPEAVApplicabilityContext@@@Z`
- size: `251`
- prototype: `void __fastcall(void *, struct ApplicabilityContext *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800098c0`

## callees

- `0x180009984`
- `0x180009a88`
- `0x18000d6f4`
- `0x18001686c`
- `0x1800227c0`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180009a3c`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180009a3c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800099ca`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800099ca`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall AddScaleFactors(void *a1, struct ApplicabilityContext *a2)
{
  const unsigned __int16 **v2; // rbp
  void *v4; // rdx
  unsigned int v5; // r8d
  const char *v6; // r9
  ScaleFactorInfo *v7; // rdi
  int i; // ebx
  __int64 (__fastcall ***v9)(_QWORD, _QWORD); // rax
  int v10; // eax
  int v11; // [rsp+20h] [rbp-20h]
  LPWSTR StringSid[56]; // [rsp+40h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+1C8h]

  StringSid[53] = (LPWSTR)-2LL;
  v2 = (const unsigned __int16 **)((unsigned __int64)StringSid & 0xFFFFFFFFFFFFFFE0uLL);
  *(_QWORD *)((unsigned __int64)StringSid & 0xFFFFFFFFFFFFFFE0uLL) = 0;
  if ( !ConvertSidToStringSidW(a1, (LPWSTR *)((unsigned __int64)StringSid & 0xFFFFFFFFFFFFFFE0uLL)) )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, v4, v5, v6);
  v7 = ScaleFactorInfo::ScaleFactorInfo((ScaleFactorInfo *)(v2 + 4), *v2);
  for ( i = 0; i < *(_DWORD *)v7; ++i )
  {
    v9 = (__int64 (__fastcall ***)(_QWORD, _QWORD))(*(__int64 (__fastcall **)(struct ApplicabilityContext *))(*(_QWORD *)a2 + 8LL))(a2);
    v10 = (**v9)(v9, *((unsigned int *)v7 + 8 * i + 10));
    if ( v10 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x4F,
        (unsigned int)"onecoreuap\\base\\mrt\\applicability\\src\\scalefactorinfo.cpp",
        (const char *)(unsigned int)v10,
        v11);
  }
  if ( *v2 )
    LocalFree((HLOCAL)*v2);
}

```

## disassembly

```asm
0x180009984  mov     rax, rsp
0x180009987  push    rbp
0x180009988  push    rsi
0x180009989  push    rdi
0x18000998a  sub     rsp, 1F0h
0x180009991  mov     [rsp+200h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000999d  mov     [rax+18h], rbx
0x1800099a1  lea     rbp, [rsp+40h]
0x1800099a6  and     rbp, 0FFFFFFFFFFFFFFE0h
0x1800099aa  mov     rax, cs:__security_cookie
0x1800099b1  xor     rax, rsp
0x1800099b4  mov     [rbp+1C0h+var_20], rax
0x1800099bb  mov     rsi, rdx
0x1800099be  mov     [rbp+1C0h+StringSid], 0
0x1800099c6  lea     rdx, [rbp+1C0h+StringSid]; StringSid
0x1800099ca  call    cs:__imp_ConvertSidToStringSidW
0x1800099d0  mov     rcx, [rsp+208h]; this
0x1800099d8  test    eax, eax
0x1800099da  jz      loc_180009A79
0x1800099e0  mov     rdx, [rbp+1C0h+StringSid]; unsigned __int16 *
0x1800099e4  lea     rcx, [rbp+1C0h+var_1A0]; this
0x1800099e8  call    ??0ScaleFactorInfo@@QEAA@PEBG@Z; ScaleFactorInfo::ScaleFactorInfo(ushort const *)
0x1800099ed  mov     rdi, rax
0x1800099f0  xor     ebx, ebx
0x1800099f2  cmp     [rax], ebx
0x1800099f4  jle     short loc_180009A33
0x1800099f6  mov     rcx, [rsi]
0x1800099f9  mov     rax, [rcx+8]
0x1800099fd  mov     rcx, rsi
0x180009a00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a05  mov     r8, rax
0x180009a08  mov     rcx, [rax]
0x180009a0b  movsxd  rdx, ebx
0x180009a0e  shl     rdx, 5
0x180009a12  mov     rax, [rcx]
0x180009a15  mov     edx, [rdx+rdi+28h]
0x180009a19  mov     rcx, r8
0x180009a1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a21  mov     rcx, [rsp+208h]; this
0x180009a29  test    eax, eax
0x180009a2b  js      short loc_180009A64
0x180009a2d  inc     ebx
0x180009a2f  cmp     ebx, [rdi]
0x180009a31  jl      short loc_1800099F6
0x180009a33  mov     rcx, [rbp+1C0h+StringSid]; hMem
0x180009a37  test    rcx, rcx
0x180009a3a  jz      short loc_180009A42
0x180009a3c  call    cs:__imp_LocalFree
0x180009a42  mov     rcx, [rbp+1C0h+var_20]
0x180009a49  xor     rcx, rsp; StackCookie
0x180009a4c  call    __security_check_cookie
0x180009a51  mov     rbx, [rsp+200h+arg_10]
0x180009a59  add     rsp, 1F0h
0x180009a60  pop     rdi
0x180009a61  pop     rsi
0x180009a62  pop     rbp
0x180009a63  retn
0x180009a64  mov     r9d, eax; char *
0x180009a67  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\mrt\\applicability\\s"...
0x180009a6e  mov     edx, 4Fh ; 'O'; void *
0x180009a73  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180009a79  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
