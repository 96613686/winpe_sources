# ShieldProvider::DataProtectionShield::WaitForWscServiceStatusChange(bool)

- ea: `0x18007b210`
- end: `0x18007b37c`
- name: `?WaitForWscServiceStatusChange@DataProtectionShield@ShieldProvider@@AEAAJ_N@Z`
- size: `364`
- prototype: `__int64 __fastcall(ShieldProvider::DataProtectionShield *__hidden this, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18007b390`

## callees

- `0x180004710`
- `0x18000517c`
- `0x18000a7ec`
- `0x18000d7fc`
- `0x18007b210`

## import_xrefs

- `KERNEL32!WaitForMultipleObjectsEx` at `0x18007b2fb`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18007b2fb`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x18007b272`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x18007b272`

## string_xrefs

- `0x18007b345`: `onecore\amcore\antimalware\source\shieldprovider\shieldproviderservice\dataprotectionshield\dataprotectionshield.cpp`

## pseudocode

```c
__int64 __fastcall ShieldProvider::DataProtectionShield::WaitForWscServiceStatusChange(
        ShieldProvider::DataProtectionShield *this,
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
  pNotifyBuffer.pfnNotifyCallback = (PFN_SC_NOTIFY_CALLBACK)ShieldProvider::DataProtectionShield::ServiceNotifyCallback;
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids, v6);
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
      (void *)0x62B,
      (unsigned int)"onecore\\amcore\\antimalware\\source\\shieldprovider\\shieldproviderservice\\dataprotectionshield\\d"
                    "ataprotectionshield.cpp",
      (const char *)v6,
      bAlertable);
  }
  return v6;
}

```

## disassembly

```asm
0x18007b210  mov     [rsp+arg_8], rbx
0x18007b215  push    rdi
0x18007b216  sub     rsp, 0A0h
0x18007b21d  mov     rax, cs:__security_cookie
0x18007b224  xor     rax, rsp
0x18007b227  mov     [rsp+0A8h+var_18], rax
0x18007b22f  mov     bl, dl
0x18007b231  mov     rdi, rcx
0x18007b234  xor     edx, edx; Val
0x18007b236  lea     rcx, [rsp+0A8h+pNotifyBuffer]; void *
0x18007b23b  lea     r8d, [rdx+50h]; Size
0x18007b23f  call    memset_0
0x18007b244  mov     rcx, [rdi+88h]; hService
0x18007b24b  lea     rax, ?ServiceNotifyCallback@DataProtectionShield@ShieldProvider@@CAXPEAX@Z; ShieldProvider::DataProtectionShield::ServiceNotifyCallback(void *)
0x18007b252  neg     bl
0x18007b254  mov     [rsp+0A8h+pNotifyBuffer.dwVersion], 2
0x18007b25c  lea     r8, [rsp+0A8h+pNotifyBuffer]; pNotifyBuffer
0x18007b261  mov     [rsp+0A8h+pNotifyBuffer.pfnNotifyCallback], rax
0x18007b266  sbb     edx, edx
0x18007b268  mov     [rsp+0A8h+pNotifyBuffer.pContext], rdi
0x18007b26d  and     edx, 7
0x18007b270  inc     edx; dwNotifyMask
0x18007b272  call    cs:__imp_NotifyServiceStatusChangeW
0x18007b278  mov     ebx, eax
0x18007b27a  test    eax, eax
0x18007b27c  jz      short loc_18007B2CB
0x18007b27e  jle     short loc_18007B289
0x18007b280  movzx   ebx, ax
0x18007b283  or      ebx, 80070000h
0x18007b289  test    ebx, ebx
0x18007b28b  jns     short loc_18007B2CB
0x18007b28d  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b294  lea     rax, WPP_GLOBAL_Control
0x18007b29b  cmp     rcx, rax
0x18007b29e  jz      loc_18007B359
0x18007b2a4  test    byte ptr [rcx+1Ch], 1
0x18007b2a8  jz      loc_18007B359
0x18007b2ae  mov     rcx, [rcx+10h]
0x18007b2b2  lea     r8, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids
0x18007b2b9  mov     edx, 53h ; 'S'
0x18007b2be  mov     r9d, ebx
0x18007b2c1  call    WPP_SF_d
0x18007b2c6  jmp     loc_18007B359
0x18007b2cb  mov     rax, cs:?g_ahServiceStoppingEvent@ShieldProvider@@3PEAXEA; void * ShieldProvider::g_ahServiceStoppingEvent
0x18007b2d2  lea     rdx, [rsp+0A8h+Handles]; lpHandles
0x18007b2d7  xor     r8d, r8d; bWaitAll
0x18007b2da  mov     [rsp+0A8h+Handles], rax
0x18007b2df  mov     rax, [rdi+98h]
0x18007b2e6  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18007b2ea  mov     [rsp+0A8h+var_70], rax
0x18007b2ef  mov     [rsp+0A8h+bAlertable], 1; int
0x18007b2f7  lea     ecx, [r8+2]; nCount
0x18007b2fb  call    cs:__imp_WaitForMultipleObjectsEx
0x18007b301  test    eax, eax
0x18007b303  jz      short loc_18007B338
0x18007b305  cmp     eax, 1
0x18007b308  jz      short loc_18007B338
0x18007b30a  cmp     eax, 80h
0x18007b30f  jz      short loc_18007B331
0x18007b311  cmp     eax, 81h
0x18007b316  jz      short loc_18007B331
0x18007b318  cmp     eax, 0C0h
0x18007b31d  jz      short loc_18007B32D
0x18007b31f  cmp     eax, 102h
0x18007b324  jnz     short loc_18007B331
0x18007b326  mov     ebx, 800705B4h
0x18007b32b  jmp     short loc_18007B33D
0x18007b32d  xor     eax, eax
0x18007b32f  jmp     short loc_18007B35B
0x18007b331  mov     ebx, 80004005h
0x18007b336  jmp     short loc_18007B33D
0x18007b338  mov     ebx, 80004004h
0x18007b33d  mov     rcx, [rsp+0A8h]; this
0x18007b345  lea     r8, aOnecoreAmcoreA_6; "onecore\\amcore\\antimalware\\source\\s"...
0x18007b34c  mov     r9d, ebx; char *
0x18007b34f  mov     edx, 62Bh; void *
0x18007b354  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b359  mov     eax, ebx
0x18007b35b  mov     rcx, [rsp+0A8h+var_18]
0x18007b363  xor     rcx, rsp; StackCookie
0x18007b366  call    __security_check_cookie
0x18007b36b  mov     rbx, [rsp+0A8h+arg_8]
0x18007b373  add     rsp, 0A0h
0x18007b37a  pop     rdi
0x18007b37b  retn
```
