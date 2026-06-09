# ABO_NODE::FindNode(ushort const *,ABO_NODE * *)

- ea: `0x180007ac8`
- end: `0x180007d44`
- name: `?FindNode@ABO_NODE@@QEAAJPEBGPEAPEAV1@@Z`
- size: `636`
- prototype: `void __fastcall __noreturn(ABO_NODE *__hidden this, const unsigned __int16 *, struct ABO_NODE **)`
- caller_count: `27`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180004b80`
- `0x180005cf4`
- `0x180006f54`
- `0x180009488`
- `0x18000ae70`
- `0x18000b770`
- `0x18000baec`
- `0x18000bf00`
- `0x18000c560`
- `0x18000c990`
- `0x18000cbb0`
- `0x18000cd68`
- `0x18000ce90`
- `0x18000d040`
- `0x18000d360`
- `0x18000d5d8`
- `0x18000d8f0`
- `0x18000db80`
- `0x18000dea0`
- `0x18000e170`
- `0x18000e3e0`
- `0x18000e6e0`
- `0x18000ed00`
- `0x18000f110`
- `0x18000f390`
- `0x180010f40`
- `0x180016b1c`

## callees

- `0x18000341a`
- `0x180003460`
- `0x18000473c`
- `0x180005e94`
- `0x180007ac8`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180007c9b`
- `msvcrt!_wcsicmp` at `0x180007c9b`
- `msvcrt!wcschr` at `0x180007bc7`
- `msvcrt!wcschr` at `0x180007bc7`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180007ba0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180007c17`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180007c39`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180007c55`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180007ba0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180007c17`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180007c39`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180007c55`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180007c8f`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180007c8f`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180007b26`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180007b4c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180007b71`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180007b26`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180007b4c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180007b71`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007cfc`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007d07`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007d12`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007cfc`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007d07`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007d12`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x180007c66`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x180007c66`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180007bba`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180007bda`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180007bee`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180007c2b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180007c47`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180007c7a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180007bba`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180007bda`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180007bee`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180007c2b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180007c47`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180007c7a`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x180007cdf`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x180007cdf`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180007bff`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180007bff`

## pseudocode

```c
void __fastcall __noreturn ABO_NODE::FindNode(ABO_NODE *this, const unsigned __int16 *a2, struct ABO_NODE **a3)
{
  const unsigned __int16 *v6; // rdx
  const wchar_t *Str; // rax
  wchar_t *v8; // rax
  wchar_t *v9; // r14
  __int64 v10; // rbx
  const unsigned __int16 *v11; // rax
  const unsigned __int16 *v12; // rax
  const unsigned __int16 *v13; // rax
  __int64 v14; // r14
  const wchar_t *v15; // rbx
  const wchar_t *v16; // rax
  _BYTE v17[56]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v18[56]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v19[64]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v20[256]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v21[256]; // [rsp+2D0h] [rbp+1D0h] BYREF
  unsigned __int16 v22[256]; // [rsp+4D0h] [rbp+3D0h] BYREF

  memset_0(v20, 0, sizeof(v20));
  STRU::STRU((STRU *)v18, v20, 0x100u);
  memset_0(v21, 0, sizeof(v21));
  STRU::STRU((STRU *)v17, v21, 0x100u);
  memset_0(v22, 0, sizeof(v22));
  STRU::STRU((STRU *)v19, v22, 0x100u);
  if ( a2 && a3 )
  {
    v6 = a2 + 1;
    if ( *a2 != 47 )
      v6 = a2;
    if ( (int)STRU::Copy((STRU *)v17, v6) >= 0 )
    {
      while ( 1 )
      {
        ABO_NODE::ReferenceAboNode(this);
        if ( STRU::IsEmpty((STRU *)v17) )
        {
          *a3 = this;
          break;
        }
        Str = STRU::QueryStr((STRU *)v17);
        v8 = wcschr(Str, 0x2Fu);
        v9 = v8;
        if ( v8 )
        {
          v10 = v8 - STRU::QueryStr((STRU *)v17);
          v11 = STRU::QueryStr((STRU *)v17);
          if ( (int)STRU::Copy((STRU *)v18, v11, v10) < 0
            || (int)STRU::Copy((STRU *)v19, v9 + 1) < 0
            || (v12 = STRU::QueryStr((STRU *)v19), (int)STRU::Copy((STRU *)v17, v12) < 0) )
          {
LABEL_17:
            if ( this )
              ABO_NODE::DereferenceAboNode(this);
            break;
          }
        }
        else
        {
          v13 = STRU::QueryStr((STRU *)v17);
          if ( (int)STRU::Copy((STRU *)v18, v13) < 0 )
            goto LABEL_17;
          STRU::Reset((STRU *)v17);
        }
        v14 = 0;
        if ( !*((_DWORD *)this + 10) )
          goto LABEL_17;
        while ( 1 )
        {
          v15 = STRU::QueryStr((STRU *)v18);
          v16 = STRU::QueryStr((STRU *)(*(_QWORD *)(*((_QWORD *)this + 4) + 8 * v14) + 56LL));
          if ( !_wcsicmp(v16, v15) )
            break;
          v14 = (unsigned int)(v14 + 1);
          if ( (unsigned int)v14 >= *((_DWORD *)this + 10) )
            goto LABEL_17;
        }
        ABO_NODE::DereferenceAboNode(this);
        this = *(ABO_NODE **)(*((_QWORD *)this + 4) + 8 * v14);
      }
    }
  }
  STRU::~STRU((STRU *)v19);
  STRU::~STRU((STRU *)v17);
  STRU::~STRU((STRU *)v18);
}

```

## disassembly

```asm
0x180007ac8  mov     [rsp-8+arg_18], rbx
0x180007acd  push    rbp
0x180007ace  push    rsi
0x180007acf  push    rdi
0x180007ad0  push    r12
0x180007ad2  push    r13
0x180007ad4  push    r14
0x180007ad6  push    r15
0x180007ad8  lea     rbp, [rsp-5E0h]
0x180007ae0  sub     rsp, 6E0h
0x180007ae7  mov     rax, cs:__security_cookie
0x180007aee  xor     rax, rsp
0x180007af1  mov     [rbp+610h+var_40], rax
0x180007af8  mov     r12, r8
0x180007afb  mov     rbx, rdx
0x180007afe  mov     rsi, rcx
0x180007b01  mov     r14d, 200h
0x180007b07  mov     r8d, r14d; Size
0x180007b0a  lea     rcx, [rbp+610h+var_640]; void *
0x180007b0e  xor     edx, edx; Val
0x180007b10  call    memset_0
0x180007b15  mov     edi, 100h
0x180007b1a  lea     rdx, [rbp+610h+var_640]
0x180007b1e  mov     r8d, edi
0x180007b21  lea     rcx, [rsp+710h+var_6B8]
0x180007b26  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z
0x180007b2c  mov     r8d, r14d; Size
0x180007b2f  lea     rcx, [rbp+610h+var_440]; void *
0x180007b36  xor     edx, edx; Val
0x180007b38  call    memset_0
0x180007b3d  mov     r8d, edi
0x180007b40  lea     rdx, [rbp+610h+var_440]
0x180007b47  lea     rcx, [rsp+710h+var_6F0]
0x180007b4c  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z
0x180007b52  mov     r8d, r14d; Size
0x180007b55  lea     rcx, [rbp+610h+var_240]; void *
0x180007b5c  xor     edx, edx; Val
0x180007b5e  call    memset_0
0x180007b63  mov     r8d, edi
0x180007b66  lea     rdx, [rbp+610h+var_240]
0x180007b6d  lea     rcx, [rbp+610h+var_680]
0x180007b71  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z
0x180007b77  test    rbx, rbx
0x180007b7a  jz      loc_180007CF3
0x180007b80  test    r12, r12
0x180007b83  jz      loc_180007CF3
0x180007b89  mov     r13d, 2Fh ; '/'
0x180007b8f  lea     rdx, [rbx+2]
0x180007b93  cmp     [rbx], r13w
0x180007b97  lea     rcx, [rsp+710h+var_6F0]
0x180007b9c  cmovnz  rdx, rbx
0x180007ba0  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z
0x180007ba6  mov     edi, eax
0x180007ba8  test    eax, eax
0x180007baa  js      loc_180007CF8
0x180007bb0  jmp     loc_180007CD2
0x180007bb5  lea     rcx, [rsp+710h+var_6F0]
0x180007bba  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ
0x180007bc0  mov     rcx, rax; Str
0x180007bc3  movzx   edx, r13w; Ch
0x180007bc7  call    cs:__imp_wcschr
0x180007bcd  lea     rcx, [rsp+710h+var_6F0]
0x180007bd2  mov     r14, rax
0x180007bd5  test    rax, rax
0x180007bd8  jz      short loc_180007C47
0x180007bda  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ
0x180007be0  mov     rbx, r14
0x180007be3  lea     rcx, [rsp+710h+var_6F0]
0x180007be8  sub     rbx, rax
0x180007beb  sar     rbx, 1
0x180007bee  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ
0x180007bf4  mov     r8d, ebx
0x180007bf7  lea     rcx, [rsp+710h+var_6B8]
0x180007bfc  mov     rdx, rax
0x180007bff  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z
0x180007c05  mov     edi, eax
0x180007c07  test    eax, eax
0x180007c09  js      loc_180007CB3
0x180007c0f  lea     rdx, [r14+2]
0x180007c13  lea     rcx, [rbp+610h+var_680]
0x180007c17  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z
0x180007c1d  mov     edi, eax
0x180007c1f  test    eax, eax
0x180007c21  js      loc_180007CB3
0x180007c27  lea     rcx, [rbp+610h+var_680]
0x180007c2b  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ
0x180007c31  mov     rdx, rax
0x180007c34  lea     rcx, [rsp+710h+var_6F0]
0x180007c39  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z
0x180007c3f  mov     edi, eax
0x180007c41  test    eax, eax
0x180007c43  js      short loc_180007CB3
0x180007c45  jmp     short loc_180007C6C
0x180007c47  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ
0x180007c4d  mov     rdx, rax
0x180007c50  lea     rcx, [rsp+710h+var_6B8]
0x180007c55  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z
0x180007c5b  mov     edi, eax
0x180007c5d  test    eax, eax
0x180007c5f  js      short loc_180007CB3
0x180007c61  lea     rcx, [rsp+710h+var_6F0]
0x180007c66  call    cs:__imp_?Reset@STRU@@QEAAXXZ
0x180007c6c  xor     r14d, r14d
0x180007c6f  cmp     [rsi+28h], r14d
0x180007c73  jbe     short loc_180007CAE
0x180007c75  lea     rcx, [rsp+710h+var_6B8]
0x180007c7a  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ
0x180007c80  mov     rcx, [rsi+20h]
0x180007c84  mov     rbx, rax
0x180007c87  mov     rcx, [rcx+r14*8]
0x180007c8b  add     rcx, 38h ; '8'
0x180007c8f  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ
0x180007c95  mov     rcx, rax; String1
0x180007c98  mov     rdx, rbx; String2
0x180007c9b  call    cs:__imp__wcsicmp
0x180007ca1  test    eax, eax
0x180007ca3  jz      short loc_180007CC2
0x180007ca5  inc     r14d
0x180007ca8  cmp     r14d, [rsi+28h]
0x180007cac  jb      short loc_180007C75
0x180007cae  mov     edi, 80070003h
0x180007cb3  test    rsi, rsi
0x180007cb6  jz      short loc_180007CF8
0x180007cb8  mov     rcx, rsi; this
0x180007cbb  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ
0x180007cc0  jmp     short loc_180007CF8
0x180007cc2  mov     rcx, rsi; this
0x180007cc5  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ
0x180007cca  mov     rax, [rsi+20h]
0x180007cce  mov     rsi, [rax+r14*8]
0x180007cd2  mov     rcx, rsi; this
0x180007cd5  call    ?ReferenceAboNode@ABO_NODE@@QEAAXXZ
0x180007cda  lea     rcx, [rsp+710h+var_6F0]
0x180007cdf  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ
0x180007ce5  test    al, al
0x180007ce7  jz      loc_180007BB5
0x180007ced  mov     [r12], rsi
0x180007cf1  jmp     short loc_180007CF8
0x180007cf3  mov     edi, 80070057h
0x180007cf8  lea     rcx, [rbp+610h+var_680]
0x180007cfc  call    cs:__imp_??1STRU@@QEAA@XZ
0x180007d02  lea     rcx, [rsp+710h+var_6F0]
0x180007d07  call    cs:__imp_??1STRU@@QEAA@XZ
0x180007d0d  lea     rcx, [rsp+710h+var_6B8]
0x180007d12  call    cs:__imp_??1STRU@@QEAA@XZ
0x180007d18  mov     eax, edi
0x180007d1a  mov     rcx, [rbp+610h+var_40]
0x180007d21  xor     rcx, rsp; StackCookie
0x180007d24  call    __security_check_cookie
0x180007d29  mov     rbx, [rsp+710h+arg_18]
0x180007d31  add     rsp, 6E0h
0x180007d38  pop     r15
0x180007d3a  pop     r14
0x180007d3c  pop     r13
0x180007d3e  pop     r12
0x180007d40  pop     rdi
0x180007d41  pop     rsi
0x180007d42  pop     rbp
0x180007d43  retn
```
