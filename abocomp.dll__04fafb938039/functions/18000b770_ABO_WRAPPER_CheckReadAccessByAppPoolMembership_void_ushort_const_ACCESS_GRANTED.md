# ABO_WRAPPER::CheckReadAccessByAppPoolMembership(void *,ushort const *,ACCESS_GRANTED *)

- ea: `0x18000b770`
- end: `0x18000b8ff`
- name: `?CheckReadAccessByAppPoolMembership@ABO_WRAPPER@@AEAAJPEAXPEBGPEAW4ACCESS_GRANTED@@@Z`
- size: `399`
- prototype: `int(ABO_WRAPPER *__hidden this, void *, const unsigned __int16 *, enum ACCESS_GRANTED *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000b68c`

## callees

- `0x180003460`
- `0x18000473c`
- `0x180007ac8`
- `0x18000b770`
- `0x18000baec`
- `0x18000e8dc`
- `0x18000eb58`

## import_xrefs

- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000b82b`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000b868`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000b82b`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000b868`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000b8cf`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000b8d9`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000b8cf`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000b8d9`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18000b7a5`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18000b7af`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18000b7a5`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18000b7af`

## pseudocode

```c
__int64 __fastcall ABO_WRAPPER::CheckReadAccessByAppPoolMembership(
        ABO_WRAPPER *this,
        void *a2,
        const unsigned __int16 *a3,
        enum ACCESS_GRANTED *a4)
{
  ABO_NODE *v9; // [rsp+20h] [rbp-49h] BYREF
  _BYTE v10[48]; // [rsp+28h] [rbp-41h] BYREF
  _BYTE v11[48]; // [rsp+58h] [rbp-11h] BYREF

  BUFFER::BUFFER((BUFFER *)v11);
  BUFFER::BUFFER((BUFFER *)v10);
  v9 = 0;
  if ( a2 && a3 )
  {
    *(_DWORD *)a4 = 3;
    ABO_NODE::FindNode(*(ABO_NODE **)(*((_QWORD *)this + 3) + 16LL), a3, &v9);
  }
  BUFFER::~BUFFER((BUFFER *)v10);
  BUFFER::~BUFFER((BUFFER *)v11);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000b770  push    rbp
0x18000b772  push    rbx
0x18000b773  push    rsi
0x18000b774  push    rdi
0x18000b775  push    r13
0x18000b777  push    r14
0x18000b779  push    r15
0x18000b77b  lea     rbp, [rsp-27h]
0x18000b780  sub     rsp, 90h
0x18000b787  mov     rax, cs:__security_cookie
0x18000b78e  xor     rax, rsp
0x18000b791  mov     [rbp+57h+var_38], rax
0x18000b795  mov     r13, rcx
0x18000b798  mov     rsi, r9
0x18000b79b  lea     rcx, [rbp+57h+var_68]
0x18000b79f  mov     rbx, r8
0x18000b7a2  mov     r14, rdx
0x18000b7a5  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x18000b7ab  lea     rcx, [rbp+57h+var_98]
0x18000b7af  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x18000b7b5  xor     edi, edi
0x18000b7b7  mov     [rbp+57h+var_A0], rdi
0x18000b7bb  test    r14, r14
0x18000b7be  jz      loc_18000B8B9
0x18000b7c4  test    rbx, rbx
0x18000b7c7  jz      loc_18000B8B9
0x18000b7cd  mov     dword ptr [rsi], 3
0x18000b7d3  lea     r8, [rbp+57h+var_A0]; struct ABO_NODE **
0x18000b7d7  mov     rcx, [r13+18h]
0x18000b7db  mov     rdx, rbx; unsigned __int16 *
0x18000b7de  mov     rcx, [rcx+10h]; this
0x18000b7e2  call    ?FindNode@ABO_NODE@@QEAAJPEBGPEAPEAV1@@Z; ABO_NODE::FindNode(ushort const *,ABO_NODE * *)
0x18000b7e7  mov     rdi, [rbp+57h+var_A0]
0x18000b7eb  mov     ebx, eax
0x18000b7ed  test    eax, eax
0x18000b7ef  js      loc_18000B8BE
0x18000b7f5  mov     r8, rsi; enum ACCESS_GRANTED *
0x18000b7f8  mov     rdx, rdi; struct ABO_NODE *
0x18000b7fb  call    ?IsExemptFromAppPoolReadAccessCheck@ABO_WRAPPER@@AEAAHPEAVABO_NODE@@PEAW4ACCESS_GRANTED@@@Z; ABO_WRAPPER::IsExemptFromAppPoolReadAccessCheck(ABO_NODE *,ACCESS_GRANTED *)
0x18000b800  test    eax, eax
0x18000b802  jnz     loc_18000B8BE
0x18000b808  lea     r8, [rbp+57h+var_68]; struct BUFFER *
0x18000b80c  mov     dword ptr [rsi], 3
0x18000b812  lea     edx, [rax+5]; TokenInformationClass
0x18000b815  mov     rcx, r14; TokenHandle
0x18000b818  call    ?GetTokenInformationHelper@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAVBUFFER@@@Z; GetTokenInformationHelper(void *,_TOKEN_INFORMATION_CLASS,BUFFER *)
0x18000b81d  mov     ebx, eax
0x18000b81f  test    eax, eax
0x18000b821  js      loc_18000B8BE
0x18000b827  lea     rcx, [rbp+57h+var_68]
0x18000b82b  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000b831  mov     r9, rsi; enum ACCESS_GRANTED *
0x18000b834  mov     rdx, rdi; struct ABO_NODE *
0x18000b837  mov     rcx, r13; this
0x18000b83a  mov     r8, [rax]; void *
0x18000b83d  call    ?CheckReadAccessByAppPoolSidOnSpecifiedNode@ABO_WRAPPER@@AEAAJPEAVABO_NODE@@PEAXPEAW4ACCESS_GRANTED@@@Z; ABO_WRAPPER::CheckReadAccessByAppPoolSidOnSpecifiedNode(ABO_NODE *,void *,ACCESS_GRANTED *)
0x18000b842  mov     ebx, eax
0x18000b844  test    eax, eax
0x18000b846  js      short loc_18000B8BE
0x18000b848  cmp     dword ptr [rsi], 3
0x18000b84b  jnz     short loc_18000B8BE
0x18000b84d  lea     r8, [rbp+57h+var_98]; struct BUFFER *
0x18000b851  mov     edx, 2; TokenInformationClass
0x18000b856  mov     rcx, r14; TokenHandle
0x18000b859  call    ?GetTokenInformationHelper@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAVBUFFER@@@Z; GetTokenInformationHelper(void *,_TOKEN_INFORMATION_CLASS,BUFFER *)
0x18000b85e  mov     ebx, eax
0x18000b860  test    eax, eax
0x18000b862  js      short loc_18000B8BE
0x18000b864  lea     rcx, [rbp+57h+var_98]
0x18000b868  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000b86e  mov     r14, rax
0x18000b871  mov     edx, [rax]
0x18000b873  test    edx, edx
0x18000b875  jz      short loc_18000B8BE
0x18000b877  xor     r15d, r15d
0x18000b87a  mov     r8d, r15d
0x18000b87d  not     r8d
0x18000b880  add     r8d, edx
0x18000b883  add     r8, r8
0x18000b886  test    byte ptr [r14+r8*8+10h], 4
0x18000b88c  jz      short loc_18000B8AC
0x18000b88e  mov     r8, [r14+r8*8+8]; void *
0x18000b893  mov     r9, rsi; enum ACCESS_GRANTED *
0x18000b896  mov     rdx, rdi; struct ABO_NODE *
0x18000b899  mov     rcx, r13; this
0x18000b89c  call    ?CheckReadAccessByAppPoolSidOnSpecifiedNode@ABO_WRAPPER@@AEAAJPEAVABO_NODE@@PEAXPEAW4ACCESS_GRANTED@@@Z; ABO_WRAPPER::CheckReadAccessByAppPoolSidOnSpecifiedNode(ABO_NODE *,void *,ACCESS_GRANTED *)
0x18000b8a1  mov     ebx, eax
0x18000b8a3  test    eax, eax
0x18000b8a5  js      short loc_18000B8BE
0x18000b8a7  cmp     dword ptr [rsi], 3
0x18000b8aa  jnz     short loc_18000B8BE
0x18000b8ac  mov     edx, [r14]
0x18000b8af  inc     r15d
0x18000b8b2  cmp     r15d, edx
0x18000b8b5  jb      short loc_18000B87A
0x18000b8b7  jmp     short loc_18000B8BE
0x18000b8b9  mov     ebx, 80070057h
0x18000b8be  test    rdi, rdi
0x18000b8c1  jz      short loc_18000B8CB
0x18000b8c3  mov     rcx, rdi; this
0x18000b8c6  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x18000b8cb  lea     rcx, [rbp+57h+var_98]
0x18000b8cf  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000b8d5  lea     rcx, [rbp+57h+var_68]
0x18000b8d9  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000b8df  mov     eax, ebx
0x18000b8e1  mov     rcx, [rbp+57h+var_38]
0x18000b8e5  xor     rcx, rsp; StackCookie
0x18000b8e8  call    __security_check_cookie
0x18000b8ed  add     rsp, 90h
0x18000b8f4  pop     r15
0x18000b8f6  pop     r14
0x18000b8f8  pop     r13
0x18000b8fa  pop     rdi
0x18000b8fb  pop     rsi
0x18000b8fc  pop     rbx
0x18000b8fd  pop     rbp
0x18000b8fe  retn
```
