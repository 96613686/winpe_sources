# ShieldProvider::ForceFieldShield::WaitForWscServiceStatusChange(bool)

- ea: `0x1800c1a14`
- end: `0x1800c1b80`
- name: `?WaitForWscServiceStatusChange@ForceFieldShield@ShieldProvider@@AEAAJ_N@Z`
- size: `364`
- prototype: `__int64 __fastcall(ShieldProvider::ForceFieldShield *__hidden this, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800c1b90`

## callees

- `0x180004710`
- `0x18000517c`
- `0x18000a7ec`
- `0x18000d7fc`
- `0x1800c1a14`

## import_xrefs

- `KERNEL32!WaitForMultipleObjectsEx` at `0x1800c1aff`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x1800c1aff`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x1800c1a76`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x1800c1a76`

## string_xrefs

- `0x1800c1b49`: `onecore\amcore\antimalware\source\shieldprovider\shieldproviderservice\forcefieldshield\forcefieldshield.cpp`

## pseudocode

```c
__int64 __fastcall ShieldProvider::ForceFieldShield::WaitForWscServiceStatusChange(
        ShieldProvider::ForceFieldShield *this,
        char a2)
{
  SC_HANDLE v4; // rcx
  signed int v5; // eax
  unsigned int v6; // ebx
  DWORD v7; // eax
  BOOL bAlertable; // [rsp+20h] [rbp-88h]
  HANDLE Handles[2]; // [rsp+30h] [rbp-78h] BYREF
  SERVICE_NOTIFY_2W pNotifyBuffer; // [rsp+40h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  memset_0(&pNotifyBuffer, 0, sizeof(pNotifyBuffer));
  v4 = (SC_HANDLE)*((_QWORD *)this + 17);
  pNotifyBuffer.dwVersion = 2;
  pNotifyBuffer.pfnNotifyCallback = (PFN_SC_NOTIFY_CALLBACK)ShieldProvider::ForceFieldShield::ServiceNotifyCallback;
  pNotifyBuffer.pContext = this;
  v5 = NotifyServiceStatusChangeW(v4, a2 != 0 ? 8 : 1, &pNotifyBuffer);
  v6 = v5;
  if ( !v5 )
    goto LABEL_8;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  if ( (v6 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_3533d4a562073f930570ad4a944aa956_Traceguids, v6);
  }
  else
  {
LABEL_8:
    Handles[0] = ShieldProvider::g_ahServiceStoppingEvent;
    Handles[1] = *((HANDLE *)this + 19);
    v7 = WaitForMultipleObjectsEx(2u, Handles, 0, 0xFFFFFFFF, 1);
    if ( v7 < 2 )
    {
      v6 = -2147467260;
    }
    else
    {
      if ( v7 == 128 || v7 == 129 )
        goto LABEL_15;
      if ( v7 == 192 )
        return 0;
      if ( v7 != 258 )
LABEL_15:
        v6 = -2147467259;
      else
        v6 = -2147023436;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x500,
      (unsigned int)"onecore\\amcore\\antimalware\\source\\shieldprovider\\shieldproviderservice\\forcefieldshield\\forcefieldshield.cpp",
      (const char *)v6,
      bAlertable);
  }
  return v6;
}

```

## disassembly

```asm
0x1800c1a14  mov     [rsp+arg_8], rbx
0x1800c1a19  push    rdi
0x1800c1a1a  sub     rsp, 0A0h
0x1800c1a21  mov     rax, cs:__security_cookie
0x1800c1a28  xor     rax, rsp
0x1800c1a2b  mov     [rsp+0A8h+var_18], rax
0x1800c1a33  mov     bl, dl
0x1800c1a35  mov     rdi, rcx
0x1800c1a38  xor     edx, edx; Val
0x1800c1a3a  lea     rcx, [rsp+0A8h+pNotifyBuffer]; void *
0x1800c1a3f  lea     r8d, [rdx+50h]; Size
0x1800c1a43  call    memset_0
0x1800c1a48  mov     rcx, [rdi+88h]; hService
0x1800c1a4f  lea     rax, ?ServiceNotifyCallback@ForceFieldShield@ShieldProvider@@CAXPEAX@Z; ShieldProvider::ForceFieldShield::ServiceNotifyCallback(void *)
0x1800c1a56  neg     bl
0x1800c1a58  mov     [rsp+0A8h+pNotifyBuffer.dwVersion], 2
0x1800c1a60  lea     r8, [rsp+0A8h+pNotifyBuffer]; pNotifyBuffer
0x1800c1a65  mov     [rsp+0A8h+pNotifyBuffer.pfnNotifyCallback], rax
0x1800c1a6a  sbb     edx, edx
0x1800c1a6c  mov     [rsp+0A8h+pNotifyBuffer.pContext], rdi
0x1800c1a71  and     edx, 7
0x1800c1a74  inc     edx; dwNotifyMask
0x1800c1a76  call    cs:__imp_NotifyServiceStatusChangeW
0x1800c1a7c  mov     ebx, eax
0x1800c1a7e  test    eax, eax
0x1800c1a80  jz      short loc_1800C1ACF
0x1800c1a82  jle     short loc_1800C1A8D
0x1800c1a84  movzx   ebx, ax
0x1800c1a87  or      ebx, 80070000h
0x1800c1a8d  test    ebx, ebx
0x1800c1a8f  jns     short loc_1800C1ACF
0x1800c1a91  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c1a98  lea     rax, WPP_GLOBAL_Control
0x1800c1a9f  cmp     rcx, rax
0x1800c1aa2  jz      loc_1800C1B5D
0x1800c1aa8  test    byte ptr [rcx+1Ch], 1
0x1800c1aac  jz      loc_1800C1B5D
0x1800c1ab2  mov     rcx, [rcx+10h]
0x1800c1ab6  lea     r8, WPP_3533d4a562073f930570ad4a944aa956_Traceguids
0x1800c1abd  mov     edx, 43h ; 'C'
0x1800c1ac2  mov     r9d, ebx
0x1800c1ac5  call    WPP_SF_d
0x1800c1aca  jmp     loc_1800C1B5D
0x1800c1acf  mov     rax, cs:?g_ahServiceStoppingEvent@ShieldProvider@@3PEAXEA; void * ShieldProvider::g_ahServiceStoppingEvent
0x1800c1ad6  lea     rdx, [rsp+0A8h+Handles]; lpHandles
0x1800c1adb  xor     r8d, r8d; bWaitAll
0x1800c1ade  mov     [rsp+0A8h+Handles], rax
0x1800c1ae3  mov     rax, [rdi+98h]
0x1800c1aea  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800c1aee  mov     [rsp+0A8h+var_70], rax
0x1800c1af3  mov     [rsp+0A8h+bAlertable], 1; int
0x1800c1afb  lea     ecx, [r8+2]; nCount
0x1800c1aff  call    cs:__imp_WaitForMultipleObjectsEx
0x1800c1b05  test    eax, eax
0x1800c1b07  jz      short loc_1800C1B3C
0x1800c1b09  cmp     eax, 1
0x1800c1b0c  jz      short loc_1800C1B3C
0x1800c1b0e  cmp     eax, 80h
0x1800c1b13  jz      short loc_1800C1B35
0x1800c1b15  cmp     eax, 81h
0x1800c1b1a  jz      short loc_1800C1B35
0x1800c1b1c  cmp     eax, 0C0h
0x1800c1b21  jz      short loc_1800C1B31
0x1800c1b23  cmp     eax, 102h
0x1800c1b28  jnz     short loc_1800C1B35
0x1800c1b2a  mov     ebx, 800705B4h
0x1800c1b2f  jmp     short loc_1800C1B41
0x1800c1b31  xor     eax, eax
0x1800c1b33  jmp     short loc_1800C1B5F
0x1800c1b35  mov     ebx, 80004005h
0x1800c1b3a  jmp     short loc_1800C1B41
0x1800c1b3c  mov     ebx, 80004004h
0x1800c1b41  mov     rcx, [rsp+0A8h]; this
0x1800c1b49  lea     r8, aOnecoreAmcoreA_10; "onecore\\amcore\\antimalware\\source\\s"...
0x1800c1b50  mov     r9d, ebx; char *
0x1800c1b53  mov     edx, 500h; void *
0x1800c1b58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c1b5d  mov     eax, ebx
0x1800c1b5f  mov     rcx, [rsp+0A8h+var_18]
0x1800c1b67  xor     rcx, rsp; StackCookie
0x1800c1b6a  call    __security_check_cookie
0x1800c1b6f  mov     rbx, [rsp+0A8h+arg_8]
0x1800c1b77  add     rsp, 0A0h
0x1800c1b7e  pop     rdi
0x1800c1b7f  retn
```
