# FeedbackManager::SetClient(FeedbackDataLayout const *,unsigned __int64,uchar)

- ea: `0x18001bf00`
- end: `0x18001c118`
- name: `?SetClient@FeedbackManager@@QEAAXPEBVFeedbackDataLayout@@_KE@Z`
- size: `536`
- prototype: `void __fastcall(FeedbackManager *__hidden this, const struct FeedbackDataLayout *, unsigned __int64, unsigned __int8)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18003dc00`
- `0x18003ee94`

## callees

- `0x180001304`
- `0x180001414`
- `0x18001bf00`
- `0x18004c8e0`

## import_xrefs

- `ntdll!NtAlertThread` at `0x18001c087`
- `ntdll!NtAlertThread` at `0x18001c087`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c02d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c02d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c077`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c077`

## pseudocode

```c
void __fastcall FeedbackManager::SetClient(
        FeedbackManager *this,
        const struct FeedbackDataLayout *a2,
        __int64 a3,
        char a4)
{
  __int64 v8; // rax
  NTSTATUS v9; // eax
  int v10; // r8d
  int v11; // r9d
  __int64 v12; // rcx
  char v13; // [rsp+40h] [rbp-C0h] BYREF
  int v14; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v15; // [rsp+48h] [rbp-B8h] BYREF
  const char *v16; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v17; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v18[32]; // [rsp+60h] [rbp-A0h] BYREF
  const char *v19; // [rsp+80h] [rbp-80h]
  __int64 v20; // [rsp+88h] [rbp-78h]
  int *v21; // [rsp+90h] [rbp-70h]
  __int64 v22; // [rsp+98h] [rbp-68h]
  const char *v23; // [rsp+A0h] [rbp-60h]
  __int64 v24; // [rsp+A8h] [rbp-58h]
  __int16 *v25; // [rsp+B0h] [rbp-50h]
  __int64 v26; // [rsp+B8h] [rbp-48h]
  __int64 v27; // [rsp+C0h] [rbp-40h]
  __int64 v28; // [rsp+C8h] [rbp-38h]
  __int64 *v29; // [rsp+D0h] [rbp-30h]
  __int64 v30; // [rsp+D8h] [rbp-28h]
  char *v31; // [rsp+E0h] [rbp-20h]
  __int64 v32; // [rsp+E8h] [rbp-18h]

  if ( (unsigned int)dword_180069000 > 5 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
  {
    v8 = *(_QWORD *)this + 172LL;
    v31 = &v13;
    v16 = (const char *)v8;
    v27 = v8;
    v29 = &v15;
    v23 = "Assigning client to feedback manager";
    v13 = a4;
    v21 = &v14;
    v15 = a3;
    v17 = 32;
    v25 = &v17;
    v28 = 32;
    v14 = 387;
    v32 = 1;
    v30 = 8;
    v26 = 2;
    v24 = 37;
    v22 = 4;
    v19 = "onecore\\xbox\\gameinput\\feedback\\FeedbackManager.cpp";
    v20 = 52;
    tlgWriteTransfer_GameInputEventWriteTransfer(
      (__int64)&dword_180069000,
      (unsigned __int8 *)byte_18005BEE3,
      0,
      0,
      9,
      (__int64)v18);
  }
  AcquireSRWLockExclusive(*(PSRWLOCK *)this);
  *(_QWORD *)(*(_QWORD *)this + 16LL) = a2;
  *(_QWORD *)(*(_QWORD *)this + 24LL) = -1;
  *(_QWORD *)(*(_QWORD *)this + 32LL) = a3;
  *(_BYTE *)(*(_QWORD *)this + 40LL) = a4;
  _InterlockedOr8(
    (volatile signed __int8 *)(*(_QWORD *)this + 169LL),
    *(_QWORD *)(*(_QWORD *)this + 120LL) != 0 ? 7 : 1);
  ReleaseSRWLockExclusive(*(PSRWLOCK *)this);
  v9 = NtAlertThread(*((HANDLE *)this + 1));
  if ( v9 < 0 && (unsigned int)dword_180069000 > 2 && (qword_180069010 & 8) != 0 )
  {
    v12 = qword_180069018 & 8;
    if ( v12 == qword_180069018 )
    {
      v14 = v9;
      LODWORD(v15) = 416;
      v16 = "onecore\\xbox\\gameinput\\feedback\\FeedbackManager.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (unsigned int)byte_18005A2B5,
        v10,
        v11,
        (__int64)&v16,
        (__int64)&v15,
        (__int64)&v14);
    }
  }
}

```

## disassembly

```asm
0x18001bf00  push    rbp
0x18001bf02  push    rbx
0x18001bf03  push    rsi
0x18001bf04  push    rdi
0x18001bf05  push    r12
0x18001bf07  push    r14
0x18001bf09  lea     rbp, [rsp-8]
0x18001bf0e  sub     rsp, 108h
0x18001bf15  mov     rax, cs:__security_cookie
0x18001bf1c  xor     rax, rsp
0x18001bf1f  mov     [rbp+30h+var_40], rax
0x18001bf23  mov     eax, cs:dword_180069000
0x18001bf29  lea     r12, aOnecoreXboxGam_10; "onecore\\xbox\\gameinput\\feedback\\Fee"...
0x18001bf30  mov     dil, r9b
0x18001bf33  mov     rsi, r8
0x18001bf36  mov     r14, rdx
0x18001bf39  mov     rbx, rcx
0x18001bf3c  cmp     eax, 5
0x18001bf3f  jbe     loc_18001C02A
0x18001bf45  mov     rcx, cs:qword_180069018
0x18001bf4c  mov     rax, cs:qword_180069010
0x18001bf53  test    al, 8
0x18001bf55  jz      loc_18001C02A
0x18001bf5b  mov     rax, rcx
0x18001bf5e  and     eax, 8
0x18001bf61  cmp     rax, rcx
0x18001bf64  jnz     loc_18001C02A
0x18001bf6a  mov     rax, [rbx]
0x18001bf6d  lea     rcx, [rsp+130h+var_F0]
0x18001bf72  add     rax, 0ACh
0x18001bf78  mov     [rbp+30h+var_50], rcx
0x18001bf7c  mov     [rsp+130h+var_E0], rax
0x18001bf81  lea     rcx, [rsp+130h+var_E8]
0x18001bf86  mov     [rbp+30h+var_70], rax
0x18001bf8a  mov     edx, 20h ; ' '
0x18001bf8f  mov     [rbp+30h+var_60], rcx
0x18001bf93  lea     rax, aAssigningClien; "Assigning client to feedback manager"
0x18001bf9a  mov     [rbp+30h+var_90], rax
0x18001bf9e  lea     rcx, [rsp+130h+var_D8]
0x18001bfa3  lea     rax, [rsp+130h+var_EC]
0x18001bfa8  mov     [rsp+130h+var_F0], r9b
0x18001bfad  mov     [rbp+30h+var_A0], rax
0x18001bfb1  xor     r9d, r9d
0x18001bfb4  lea     rax, [rsp+130h+var_D0]
0x18001bfb9  mov     [rsp+130h+var_E8], r8
0x18001bfbe  mov     [rsp+130h+var_D8], dx
0x18001bfc3  xor     r8d, r8d
0x18001bfc6  mov     [rbp+30h+var_80], rcx
0x18001bfca  lea     rcx, dword_180069000
0x18001bfd1  mov     [rbp+30h+var_68], rdx
0x18001bfd5  lea     rdx, byte_18005BEE3
0x18001bfdc  mov     [rsp+130h+var_108], rax
0x18001bfe1  mov     dword ptr [rsp+130h+var_110], 9
0x18001bfe9  mov     [rsp+130h+var_EC], 183h
0x18001bff1  mov     [rbp+30h+var_48], 1
0x18001bff9  mov     [rbp+30h+var_58], 8
0x18001c001  mov     [rbp+30h+var_78], 2
0x18001c009  mov     [rbp+30h+var_88], 25h ; '%'
0x18001c011  mov     [rbp+30h+var_98], 4
0x18001c019  mov     [rbp+30h+var_B0], r12
0x18001c01d  mov     [rbp+30h+var_A8], 34h ; '4'
0x18001c025  call    _tlgWriteTransfer_GameInputEventWriteTransfer
0x18001c02a  mov     rcx, [rbx]; SRWLock
0x18001c02d  call    cs:__imp_AcquireSRWLockExclusive
0x18001c034  nop     dword ptr [rax+rax+00h]
0x18001c039  mov     rax, [rbx]
0x18001c03c  mov     [rax+10h], r14
0x18001c040  mov     rax, [rbx]
0x18001c043  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x18001c04b  mov     rax, [rbx]
0x18001c04e  mov     [rax+20h], rsi
0x18001c052  mov     rax, [rbx]
0x18001c055  mov     [rax+28h], dil
0x18001c059  mov     r8, [rbx]
0x18001c05c  mov     rax, [r8+78h]
0x18001c060  nop
0x18001c061  neg     rax
0x18001c064  sbb     dl, dl
0x18001c066  and     dl, 6
0x18001c069  inc     dl
0x18001c06b  lock or [r8+0A9h], dl
0x18001c073  nop
0x18001c074  mov     rcx, [rbx]; SRWLock
0x18001c077  call    cs:__imp_ReleaseSRWLockExclusive
0x18001c07e  nop     dword ptr [rax+rax+00h]
0x18001c083  mov     rcx, [rbx+8]; ThreadHandle
0x18001c087  call    cs:__imp_NtAlertThread
0x18001c08e  nop     dword ptr [rax+rax+00h]
0x18001c093  test    eax, eax
0x18001c095  jns     short loc_18001C0FB
0x18001c097  mov     ecx, cs:dword_180069000
0x18001c09d  cmp     ecx, 2
0x18001c0a0  jbe     short loc_18001C0FB
0x18001c0a2  mov     rdx, cs:qword_180069018
0x18001c0a9  mov     rcx, cs:qword_180069010
0x18001c0b0  test    cl, 8
0x18001c0b3  jz      short loc_18001C0FB
0x18001c0b5  mov     rcx, rdx
0x18001c0b8  and     ecx, 8
0x18001c0bb  cmp     rcx, rdx
0x18001c0be  jnz     short loc_18001C0FB
0x18001c0c0  mov     [rsp+130h+var_EC], eax
0x18001c0c4  lea     rdx, byte_18005A2B5
0x18001c0cb  lea     rax, [rsp+130h+var_EC]
0x18001c0d0  mov     dword ptr [rsp+130h+var_E8], 1A0h
0x18001c0d8  mov     [rsp+130h+var_100], rax
0x18001c0dd  lea     rax, [rsp+130h+var_E8]
0x18001c0e2  mov     [rsp+130h+var_108], rax
0x18001c0e7  lea     rax, [rsp+130h+var_E0]
0x18001c0ec  mov     [rsp+130h+var_110], rax
0x18001c0f1  mov     [rsp+130h+var_E0], r12
0x18001c0f6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001c0fb  mov     rcx, [rbp+30h+var_40]
0x18001c0ff  xor     rcx, rsp; StackCookie
0x18001c102  call    __security_check_cookie
0x18001c107  add     rsp, 108h
0x18001c10e  pop     r14
0x18001c110  pop     r12
0x18001c112  pop     rdi
0x18001c113  pop     rsi
0x18001c114  pop     rbx
0x18001c115  pop     rbp
0x18001c116  retn
```
