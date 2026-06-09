# CApplicationFrameInputPaneWindowService::FireDeferredInputPaneEvents(void)

- ea: `0x18002bc50`
- end: `0x18002be1b`
- name: `?FireDeferredInputPaneEvents@CApplicationFrameInputPaneWindowService@@QEAAJXZ`
- size: `459`
- prototype: `__int64 __fastcall(CApplicationFrameInputPaneWindowService *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005cc88`
- `0x18005cde4`

## callees

- `0x18002bc50`
- `0x1800396a0`
- `0x18003ed08`
- `0x18003f804`
- `0x180040270`
- `0x1800422b8`
- `0x180043c30`
- `0x18005c438`
- `0x18005c990`
- `0x18005e480`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002bc8e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002bc8e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002bcdd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002bcdd`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x18002bcbb`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x18002bcbb`

## string_xrefs

- `0x18002bd49`: `pcshell\shell\applicationframe\frame\lib\inputpanewindowservice.cpp`
- `0x18002bd7c`: `pcshell\shell\applicationframe\frame\lib\inputpanewindowservice.cpp`

## pseudocode

```c
__int64 __fastcall CApplicationFrameInputPaneWindowService::FireDeferredInputPaneEvents(
        CApplicationFrameInputPaneWindowService *this)
{
  RTL_SRWLOCK *v1; // r15
  __int64 v3; // r12
  char v4; // si
  int v5; // eax
  char v6; // r14
  int PresentedWindowRects; // eax
  unsigned int v9; // edi
  int v10; // eax
  unsigned int v11; // edi
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // [rsp+20h] [rbp-E0h]
  char v16; // [rsp+50h] [rbp-B0h] BYREF
  int v17; // [rsp+54h] [rbp-ACh] BYREF
  CApplicationFrameInputPaneWindowService *v18; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v19; // [rsp+60h] [rbp-A0h] BYREF
  struct tagRECT rcDst; // [rsp+68h] [rbp-98h] BYREF
  struct tagRECT v21; // [rsp+78h] [rbp-88h] BYREF
  struct tagRECT v22; // [rsp+88h] [rbp-78h] BYREF
  struct tagRECT v23; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v24[96]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v1 = (RTL_SRWLOCK *)((char *)this + 80);
  rcDst = 0;
  AcquireSRWLockExclusive((PSRWLOCK)this + 10);
  v3 = *((_QWORD *)this + 12);
  v4 = *((_BYTE *)this + 89);
  v5 = *((_DWORD *)this + 23);
  v6 = *((_BYTE *)this + 88);
  v19 = v3;
  v16 = v4;
  v17 = v5;
  CopyRect(&rcDst, (const RECT *)((char *)this + 104));
  *((_BYTE *)this + 88) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_DWORD *)this + 23) = 0;
  *(_OWORD *)((char *)this + 104) = 0;
  if ( v1 )
    ReleaseSRWLockExclusive(v1);
  v21 = 0;
  v22 = 0;
  v23 = 0;
  if ( !v4 )
    goto LABEL_4;
  PresentedWindowRects = CApplicationFrameInputPaneWindowService::_GetPresentedWindowRects((HWND *)this, &v21, &v22);
  v9 = PresentedWindowRects;
  if ( PresentedWindowRects < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x52,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\inputpanewindowservice.cpp",
      (const char *)(unsigned int)PresentedWindowRects,
      v15);
    return v9;
  }
  v10 = CApplicationFrameInputPaneWindowService::_MapScreenToPresentedWindowClientRect(this, &rcDst, &v23);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x53,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\inputpanewindowservice.cpp",
      (const char *)(unsigned int)v10,
      v15);
    return v11;
  }
  else
  {
LABEL_4:
    if ( v6 )
    {
      if ( v3 )
      {
        v18 = this;
        Microsoft::WRL::ComPtr<CApplicationFrameInputPaneWindowService>::InternalAddRef(&v18);
        v12 = lambda_da07a0e4b93a96d0f294b733e0f5fabb_::_lambda_da07a0e4b93a96d0f294b733e0f5fabb_(
                (unsigned int)v24,
                (unsigned int)&v18,
                (unsigned int)&v19,
                (unsigned int)&v16,
                (__int64)&v17,
                (__int64)&rcDst,
                (__int64)&v23,
                (__int64)&v22,
                (__int64)&v21);
        Windows::Internal::ComTaskPool::QueueTask__lambda_da07a0e4b93a96d0f294b733e0f5fabb___(
          v14,
          v13,
          *((unsigned int *)this + 18),
          v12);
        Microsoft::WRL::ComPtr<CApplicationFrameInputPaneWindowService>::~ComPtr<CApplicationFrameInputPaneWindowService>(v24);
        Microsoft::WRL::ComPtr<CApplicationFrameInputPaneWindowService>::InternalRelease(&v18);
      }
    }
    return 0;
  }
}

```

## disassembly

```asm
0x18002bc50  mov     [rsp-8+arg_8], rbx
0x18002bc55  mov     [rsp-8+arg_10], rsi
0x18002bc5a  push    rbp
0x18002bc5b  push    rdi
0x18002bc5c  push    r12
0x18002bc5e  push    r14
0x18002bc60  push    r15
0x18002bc62  lea     rbp, [rsp-20h]
0x18002bc67  sub     rsp, 120h
0x18002bc6e  mov     rax, cs:__security_cookie
0x18002bc75  xor     rax, rsp
0x18002bc78  mov     [rbp+40h+var_30], rax
0x18002bc7c  lea     r15, [rcx+50h]
0x18002bc80  mov     rbx, rcx
0x18002bc83  xorps   xmm0, xmm0
0x18002bc86  mov     rcx, r15; SRWLock
0x18002bc89  movups  xmmword ptr [rsp+140h+rcDst.left], xmm0
0x18002bc8e  call    cs:__imp_AcquireSRWLockExclusive
0x18002bc94  mov     r12, [rbx+60h]
0x18002bc98  lea     rdx, [rbx+68h]; lprcSrc
0x18002bc9c  movzx   esi, byte ptr [rbx+59h]
0x18002bca0  lea     rcx, [rsp+140h+rcDst]; lprcDst
0x18002bca5  mov     eax, [rbx+5Ch]
0x18002bca8  movzx   r14d, byte ptr [rbx+58h]
0x18002bcad  mov     [rsp+140h+var_E0], r12
0x18002bcb2  mov     [rsp+140h+var_F0], sil
0x18002bcb7  mov     [rsp+140h+var_EC], eax
0x18002bcbb  call    cs:__imp_CopyRect
0x18002bcc1  xor     eax, eax
0x18002bcc3  mov     byte ptr [rbx+58h], 0
0x18002bcc7  mov     [rbx+60h], rax
0x18002bccb  xorps   xmm0, xmm0
0x18002bcce  mov     [rbx+5Ch], eax
0x18002bcd1  movups  xmmword ptr [rbx+68h], xmm0
0x18002bcd5  test    r15, r15
0x18002bcd8  jz      short loc_18002BCE3
0x18002bcda  mov     rcx, r15; SRWLock
0x18002bcdd  call    cs:__imp_ReleaseSRWLockExclusive
0x18002bce3  xorps   xmm0, xmm0
0x18002bce6  xorps   xmm1, xmm1
0x18002bce9  movups  xmmword ptr [rsp+140h+var_C8.left], xmm0
0x18002bcee  movups  xmmword ptr [rbp+40h+var_B8.left], xmm1
0x18002bcf2  movups  xmmword ptr [rbp+40h+var_A8.left], xmm0
0x18002bcf6  test    sil, sil
0x18002bcf9  jnz     short loc_18002BD2E
0x18002bcfb  test    r14b, r14b
0x18002bcfe  jnz     loc_18002BD97
0x18002bd04  xor     eax, eax
0x18002bd06  mov     rcx, [rbp+40h+var_30]
0x18002bd0a  xor     rcx, rsp; StackCookie
0x18002bd0d  call    __security_check_cookie
0x18002bd12  lea     r11, [rsp+140h+var_20]
0x18002bd1a  mov     rbx, [r11+38h]
0x18002bd1e  mov     rsi, [r11+40h]
0x18002bd22  mov     rsp, r11
0x18002bd25  pop     r15
0x18002bd27  pop     r14
0x18002bd29  pop     r12
0x18002bd2b  pop     rdi
0x18002bd2c  pop     rbp
0x18002bd2d  retn
0x18002bd2e  lea     r8, [rbp+40h+var_B8]; struct tagRECT *
0x18002bd32  mov     rcx, rbx; this
0x18002bd35  lea     rdx, [rsp+140h+var_C8]; struct tagRECT *
0x18002bd3a  call    ?_GetPresentedWindowRects@CApplicationFrameInputPaneWindowService@@AEAAJPEAUtagRECT@@0@Z; CApplicationFrameInputPaneWindowService::_GetPresentedWindowRects(tagRECT *,tagRECT *)
0x18002bd3f  mov     edi, eax
0x18002bd41  test    eax, eax
0x18002bd43  jns     short loc_18002BD61
0x18002bd45  mov     rcx, [rbp+48h]; this
0x18002bd49  lea     r8, aPcshellShellAp_9; "pcshell\\shell\\applicationframe\\frame"...
0x18002bd50  mov     r9d, eax; char *
0x18002bd53  mov     edx, 52h ; 'R'; void *
0x18002bd58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bd5d  mov     eax, edi
0x18002bd5f  jmp     short loc_18002BD06
0x18002bd61  lea     r8, [rbp+40h+var_A8]; struct tagRECT *
0x18002bd65  mov     rcx, rbx; this
0x18002bd68  lea     rdx, [rsp+140h+rcDst]; struct tagRECT *
0x18002bd6d  call    ?_MapScreenToPresentedWindowClientRect@CApplicationFrameInputPaneWindowService@@AEAAJPEBUtagRECT@@PEAU2@@Z; CApplicationFrameInputPaneWindowService::_MapScreenToPresentedWindowClientRect(tagRECT const *,tagRECT *)
0x18002bd72  mov     edi, eax
0x18002bd74  test    eax, eax
0x18002bd76  jns     short loc_18002BCFB
0x18002bd78  mov     rcx, [rbp+48h]; this
0x18002bd7c  lea     r8, aPcshellShellAp_9; "pcshell\\shell\\applicationframe\\frame"...
0x18002bd83  mov     r9d, eax; char *
0x18002bd86  mov     edx, 53h ; 'S'; void *
0x18002bd8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bd90  mov     eax, edi
0x18002bd92  jmp     loc_18002BD06
0x18002bd97  test    r12, r12
0x18002bd9a  jz      loc_18002BD04
0x18002bda0  lea     rcx, [rsp+140h+var_E8]
0x18002bda5  mov     [rsp+140h+var_E8], rbx
0x18002bdaa  call    ?InternalAddRef@?$ComPtr@VCApplicationFrameInputPaneWindowService@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<CApplicationFrameInputPaneWindowService>::InternalAddRef(void)
0x18002bdaf  lea     rax, [rsp+140h+var_C8]
0x18002bdb4  mov     [rsp+140h+var_100], rax
0x18002bdb9  lea     r9, [rsp+140h+var_F0]
0x18002bdbe  lea     rax, [rbp+40h+var_B8]
0x18002bdc2  mov     [rsp+140h+var_108], rax
0x18002bdc7  lea     r8, [rsp+140h+var_E0]
0x18002bdcc  lea     rax, [rbp+40h+var_A8]
0x18002bdd0  mov     [rsp+140h+var_110], rax
0x18002bdd5  lea     rdx, [rsp+140h+var_E8]
0x18002bdda  lea     rax, [rsp+140h+rcDst]
0x18002bddf  mov     [rsp+140h+var_118], rax
0x18002bde4  lea     rcx, [rbp+40h+var_90]
0x18002bde8  lea     rax, [rsp+140h+var_EC]
0x18002bded  mov     [rsp+140h+var_120], rax
0x18002bdf2  call    _lambda_da07a0e4b93a96d0f294b733e0f5fabb____lambda_da07a0e4b93a96d0f294b733e0f5fabb_
0x18002bdf7  mov     r8d, [rbx+48h]
0x18002bdfb  mov     r9, rax
0x18002bdfe  call    Windows__Internal__ComTaskPool__QueueTask__lambda_da07a0e4b93a96d0f294b733e0f5fabb___
0x18002be03  lea     rcx, [rbp+40h+var_90]
0x18002be07  call    ??1?$ComPtr@VCApplicationFrameInputPaneWindowService@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<CApplicationFrameInputPaneWindowService>::~ComPtr<CApplicationFrameInputPaneWindowService>(void)
0x18002be0c  lea     rcx, [rsp+140h+var_E8]
0x18002be11  call    ?InternalRelease@?$ComPtr@VCApplicationFrameInputPaneWindowService@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CApplicationFrameInputPaneWindowService>::InternalRelease(void)
0x18002be16  jmp     loc_18002BD04
```
