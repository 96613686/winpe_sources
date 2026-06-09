# CIMRequestRAEvent::InitCSP(int)

- ea: `0x140014508`
- end: `0x14001460f`
- name: `?InitCSP@CIMRequestRAEvent@@QEAAJH@Z`
- size: `263`
- prototype: `__int64 __fastcall(CIMRequestRAEvent *__hidden this, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140013ef8`
- `0x140014ccc`

## callees

- `0x140014508`
- `0x140015240`

## import_xrefs

- `ADVAPI32!CryptAcquireContextW` at `0x14001453a`
- `ADVAPI32!CryptAcquireContextW` at `0x14001453a`
- `ADVAPI32!CryptGetUserKey` at `0x140014582`
- `ADVAPI32!CryptGetUserKey` at `0x140014582`
- `ADVAPI32!CryptGenKey` at `0x1400145a6`
- `ADVAPI32!CryptGenKey` at `0x1400145a6`
- `KERNEL32!GetLastError` at `0x140014544`
- `KERNEL32!GetLastError` at `0x14001458c`
- `KERNEL32!GetLastError` at `0x1400145b0`
- `KERNEL32!GetLastError` at `0x1400145cd`
- `KERNEL32!GetLastError` at `0x140014544`
- `KERNEL32!GetLastError` at `0x14001458c`
- `KERNEL32!GetLastError` at `0x1400145b0`
- `KERNEL32!GetLastError` at `0x1400145cd`

## string_xrefs

- `0x1400145f3`: `base\diagnosis\ra\dcom\src\publickeyexch.cpp`

## pseudocode

```c
__int64 __fastcall CIMRequestRAEvent::InitCSP(CIMRequestRAEvent *this, int a2)
{
  HCRYPTPROV *v2; // rdi
  signed int LastError; // eax
  const struct _EVENT_DESCRIPTOR *v6; // rdx
  CEventLogger *v7; // rcx
  unsigned int v8; // ebx
  unsigned int v9; // r9d
  signed int v10; // eax
  signed int v11; // eax

  v2 = (HCRYPTPROV *)((char *)this + 56);
  if ( !*((_QWORD *)this + 7)
    && !CryptAcquireContextW(v2, 0, L"Microsoft Base Cryptographic Provider v1.0", 1u, 0xF0000000) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    v9 = 74;
LABEL_17:
    CEventLogger::LogError(
      v7,
      v6,
      L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
      v9,
      L"CIMRequestRAEvent::InitCSP",
      v8);
    return v8;
  }
  v8 = 0;
  if ( a2 && !*((_QWORD *)this + 8) && !CryptGetUserKey(*v2, 1u, (HCRYPTKEY *)this + 8) )
  {
    if ( GetLastError() != -2146893811 )
    {
      v11 = GetLastError();
      v8 = v11;
      if ( v11 > 0 )
        v8 = (unsigned __int16)v11 | 0x80070000;
      v9 = 112;
      goto LABEL_17;
    }
    if ( !CryptGenKey(*v2, 1u, 0, (HCRYPTKEY *)this + 8) )
    {
      v10 = GetLastError();
      v8 = v10;
      if ( v10 > 0 )
        v8 = (unsigned __int16)v10 | 0x80070000;
      v9 = 104;
      goto LABEL_17;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x140014508  push    rbx
0x14001450a  push    rbp
0x14001450b  push    rsi
0x14001450c  push    rdi
0x14001450d  sub     rsp, 38h
0x140014511  lea     rdi, [rcx+38h]
0x140014515  mov     ebp, edx
0x140014517  cmp     qword ptr [rdi], 0
0x14001451b  mov     rsi, rcx
0x14001451e  jnz     short loc_140014564
0x140014520  mov     r9d, 1; dwProvType
0x140014526  mov     [rsp+58h+dwFlags], 0F0000000h; dwFlags
0x14001452e  lea     r8, szProvider; "Microsoft Base Cryptographic Provider v"...
0x140014535  xor     edx, edx; szContainer
0x140014537  mov     rcx, rdi; phProv
0x14001453a  call    cs:__imp_CryptAcquireContextW
0x140014540  test    eax, eax
0x140014542  jnz     short loc_140014564
0x140014544  call    cs:__imp_GetLastError
0x14001454a  mov     ebx, eax
0x14001454c  test    eax, eax
0x14001454e  jle     short loc_140014559
0x140014550  movzx   ebx, ax
0x140014553  or      ebx, 80070000h
0x140014559  mov     r9d, 4Ah ; 'J'
0x14001455f  jmp     loc_1400145E8
0x140014564  xor     ebx, ebx
0x140014566  test    ebp, ebp
0x140014568  jz      loc_140014604
0x14001456e  cmp     [rsi+40h], rbx
0x140014572  jnz     loc_140014604
0x140014578  mov     rcx, [rdi]; hProv
0x14001457b  lea     r8, [rsi+40h]; phUserKey
0x14001457f  lea     edx, [rbx+1]; dwKeySpec
0x140014582  call    cs:__imp_CryptGetUserKey
0x140014588  test    eax, eax
0x14001458a  jnz     short loc_140014604
0x14001458c  call    cs:__imp_GetLastError
0x140014592  cmp     eax, 8009000Dh
0x140014597  jnz     short loc_1400145CD
0x140014599  mov     rcx, [rdi]; hProv
0x14001459c  lea     r9, [rsi+40h]; phKey
0x1400145a0  xor     r8d, r8d; dwFlags
0x1400145a3  lea     edx, [rbx+1]; Algid
0x1400145a6  call    cs:__imp_CryptGenKey
0x1400145ac  test    eax, eax
0x1400145ae  jnz     short loc_140014604
0x1400145b0  call    cs:__imp_GetLastError
0x1400145b6  mov     ebx, eax
0x1400145b8  test    eax, eax
0x1400145ba  jle     short loc_1400145C5
0x1400145bc  movzx   ebx, ax
0x1400145bf  or      ebx, 80070000h
0x1400145c5  mov     r9d, 68h ; 'h'
0x1400145cb  jmp     short loc_1400145E8
0x1400145cd  call    cs:__imp_GetLastError
0x1400145d3  mov     ebx, eax
0x1400145d5  test    eax, eax
0x1400145d7  jle     short loc_1400145E2
0x1400145d9  movzx   ebx, ax
0x1400145dc  or      ebx, 80070000h
0x1400145e2  mov     r9d, 70h ; 'p'; unsigned int
0x1400145e8  lea     rax, aCimrequestraev_3; "CIMRequestRAEvent::InitCSP"
0x1400145ef  mov     [rsp+58h+var_30], ebx; unsigned int
0x1400145f3  lea     r8, aBaseDiagnosisR; "base\\diagnosis\\ra\\dcom\\src\\publick"...
0x1400145fa  mov     qword ptr [rsp+58h+dwFlags], rax; unsigned __int16 *
0x1400145ff  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140014604  mov     eax, ebx
0x140014606  add     rsp, 38h
0x14001460a  pop     rdi
0x14001460b  pop     rsi
0x14001460c  pop     rbp
0x14001460d  pop     rbx
0x14001460e  retn
```
