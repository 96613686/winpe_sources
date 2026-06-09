# Common::StateSeparation::GetPersistedRegKeyPath(Common::StateSeparationRedirectionMapping const &,ushort const * *,unsigned __int64,ushort * *)

- ea: `0x18002bb78`
- end: `0x18002bc9e`
- name: `?GetPersistedRegKeyPath@StateSeparation@Common@@SAJAEBUStateSeparationRedirectionMapping@2@PEAPEBG_KPEAPEAG@Z`
- size: `294`
- prototype: `__int64 __fastcall(const struct Common::StateSeparationRedirectionMapping *, const unsigned __int16 **, unsigned __int64, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800237bc`
- `0x180024d40`
- `0x18002bca4`

## callees

- `0x1800041cc`
- `0x18000a3c0`
- `0x18000f62c`
- `0x18002b7b0`
- `0x18002bb78`
- `0x18002d018`
- `0x18002d584`

## string_xrefs

- `0x18002bbb3`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18002bbec`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18002bc44`: `onecore\base\appmodel\common\stateseparation.cpp`

## pseudocode

```c
__int64 __fastcall Common::StateSeparation::GetPersistedRegKeyPath(
        Common **a1,
        const unsigned __int16 **a2,
        __int64 a3,
        unsigned __int16 **a4)
{
  int PersistedRegKeyPath; // eax
  unsigned int v7; // ebx
  int v8; // eax
  __int64 v10; // rbx
  int appended; // eax
  unsigned int v12; // edi
  __int128 v13; // [rsp+20h] [rbp-20h] BYREF
  int v14; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  void *Block; // [rsp+70h] [rbp+30h] BYREF

  Block = 0;
  PersistedRegKeyPath = Common::StateSeparation::GetPersistedRegKeyPath(a1, (unsigned __int16 **)&Block);
  v7 = PersistedRegKeyPath;
  if ( PersistedRegKeyPath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
      (const char *)(unsigned int)PersistedRegKeyPath,
      v13);
LABEL_5:
    operator delete(Block);
    return v7;
  }
  v13 = 0;
  v14 = 0;
  v8 = Common::StringBuffer::InitializeFromString((Common::StringBuffer *)&v13, (unsigned __int16 *)Block);
  v7 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18E,
      (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
      (const char *)(unsigned int)v8,
      v13);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v13);
    goto LABEL_5;
  }
  v10 = 0;
  if ( a2 )
  {
    while ( !v10 && *a2 )
    {
      appended = Common::PathHelpers::AppendPathSegment((struct Common::StringBuffer *)&v13, *a2);
      v12 = appended;
      if ( appended < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x193,
          (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
          (const char *)(unsigned int)appended,
          v13);
        goto LABEL_13;
      }
      v10 = 1;
    }
  }
  v12 = 0;
  *a4 = (unsigned __int16 *)*((_QWORD *)&v13 + 1);
  *((_QWORD *)&v13 + 1) = 0;
  LODWORD(v13) = 0;
  v14 = 0;
LABEL_13:
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v13);
  operator delete(0);
  return v12;
}

```

## disassembly

```asm
0x18002bb78  mov     [rsp-18h+arg_0], rbx
0x18002bb7d  mov     [rsp-18h+arg_8], rsi
0x18002bb82  mov     [rsp-18h+Block], r8
0x18002bb87  push    rbp
0x18002bb88  push    rdi
0x18002bb89  push    r14
0x18002bb8b  mov     rbp, rsp
0x18002bb8e  sub     rsp, 40h
0x18002bb92  mov     rsi, rdx
0x18002bb95  mov     [rbp+Block], 0
0x18002bb9d  lea     rdx, [rbp+Block]; unsigned __int16 **
0x18002bba1  mov     r14, r9
0x18002bba4  call    ?GetPersistedRegKeyPath@StateSeparation@Common@@SAJAEBUStateSeparationRedirectionMapping@2@PEAPEAG@Z; Common::StateSeparation::GetPersistedRegKeyPath(Common::StateSeparationRedirectionMapping const &,ushort * *)
0x18002bba9  mov     ebx, eax
0x18002bbab  test    eax, eax
0x18002bbad  jns     short loc_18002BBC9
0x18002bbaf  mov     rcx, [rbp+18h]; this
0x18002bbb3  lea     r8, aOnecoreBaseApp_26; "onecore\\base\\appmodel\\common\\states"...
0x18002bbba  mov     r9d, eax; char *
0x18002bbbd  mov     edx, 18Ch; void *
0x18002bbc2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bbc7  jmp     short loc_18002BC09
0x18002bbc9  mov     rdx, [rbp+Block]; unsigned __int16 *
0x18002bbcd  lea     rcx, [rbp+var_20]; this
0x18002bbd1  xor     eax, eax
0x18002bbd3  xorps   xmm0, xmm0
0x18002bbd6  movups  [rbp+var_20], xmm0
0x18002bbda  mov     [rbp+var_10], eax
0x18002bbdd  call    ?InitializeFromString@StringBuffer@Common@@QEAAJPEAG@Z; Common::StringBuffer::InitializeFromString(ushort *)
0x18002bbe2  mov     ebx, eax
0x18002bbe4  test    eax, eax
0x18002bbe6  jns     short loc_18002BC16
0x18002bbe8  mov     rcx, [rbp+18h]; this
0x18002bbec  lea     r8, aOnecoreBaseApp_26; "onecore\\base\\appmodel\\common\\states"...
0x18002bbf3  mov     r9d, eax; char *
0x18002bbf6  mov     edx, 18Eh; void *
0x18002bbfb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bc00  lea     rcx, [rbp+var_20]; this
0x18002bc04  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18002bc09  mov     rcx, [rbp+Block]; Block
0x18002bc0d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002bc12  mov     eax, ebx
0x18002bc14  jmp     short loc_18002BC8B
0x18002bc16  xor     ebx, ebx
0x18002bc18  test    rsi, rsi
0x18002bc1b  jz      short loc_18002BC5A
0x18002bc1d  cmp     rbx, 1
0x18002bc21  jnb     short loc_18002BC5A
0x18002bc23  mov     rdx, [rsi+rbx*8]; unsigned __int16 *
0x18002bc27  test    rdx, rdx
0x18002bc2a  jz      short loc_18002BC5A
0x18002bc2c  lea     rcx, [rbp+var_20]; struct Common::StringBuffer *
0x18002bc30  call    ?AppendPathSegment@PathHelpers@Common@@SAJPEAVStringBuffer@2@PEBG@Z; Common::PathHelpers::AppendPathSegment(Common::StringBuffer *,ushort const *)
0x18002bc35  mov     edi, eax
0x18002bc37  test    eax, eax
0x18002bc39  js      short loc_18002BC40
0x18002bc3b  inc     rbx
0x18002bc3e  jmp     short loc_18002BC1D
0x18002bc40  mov     rcx, [rbp+18h]; this
0x18002bc44  lea     r8, aOnecoreBaseApp_26; "onecore\\base\\appmodel\\common\\states"...
0x18002bc4b  mov     r9d, eax; char *
0x18002bc4e  mov     edx, 193h; void *
0x18002bc53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bc58  jmp     short loc_18002BC79
0x18002bc5a  mov     rax, qword ptr [rbp+var_20+8]
0x18002bc5e  xor     edi, edi
0x18002bc60  mov     [r14], rax
0x18002bc63  mov     qword ptr [rbp+var_20+8], 0
0x18002bc6b  mov     dword ptr [rbp+var_20], 0
0x18002bc72  mov     [rbp+var_10], 0
0x18002bc79  lea     rcx, [rbp+var_20]; this
0x18002bc7d  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18002bc82  xor     ecx, ecx; Block
0x18002bc84  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002bc89  mov     eax, edi
0x18002bc8b  mov     rbx, [rsp+40h+arg_0]
0x18002bc90  mov     rsi, [rsp+40h+arg_8]
0x18002bc95  add     rsp, 40h
0x18002bc99  pop     r14
0x18002bc9b  pop     rdi
0x18002bc9c  pop     rbp
0x18002bc9d  retn
```
