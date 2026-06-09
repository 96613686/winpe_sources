# ServiceControl::Run(ServiceOptions const &)

- ea: `0x14000356c`
- end: `0x14000375d`
- name: `?Run@ServiceControl@@SAJAEBUServiceOptions@@@Z`
- size: `497`
- prototype: `__int64 __fastcall(const struct ServiceOptions *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task`

## callers

- `0x140007c28`

## callees

- `0x1400023e4`
- `0x14000356c`
- `0x140003760`
- `0x14000385c`
- `0x14000395c`
- `0x140003b50`
- `0x14000f9d4`
- `0x14000fcfc`
- `0x14001008c`
- `0x1400137e0`
- `0x140014c70`

## import_xrefs

- `ole32!CoSetProxyBlanket` at `0x140003694`
- `ole32!CoSetProxyBlanket` at `0x140003694`
- `ole32!CoInitializeEx` at `0x1400035d8`
- `ole32!CoInitializeEx` at `0x1400035d8`
- `ole32!CoUninitialize` at `0x1400036bb`
- `ole32!CoUninitialize` at `0x140003711`
- `ole32!CoUninitialize` at `0x1400036bb`
- `ole32!CoUninitialize` at `0x140003711`

## string_xrefs

- `0x1400036ec`: `SUCCESS: Expected error from IStandardCollectorService::DestroySession\n`

## pseudocode

```c
__int64 __fastcall ServiceControl::Run(const struct ServiceOptions *a1)
{
  unsigned int v2; // esi
  char v3; // bl
  __int64 v4; // rdx
  HRESULT v5; // edi
  __int64 v6; // r8
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  int StandardCollectorServiceForDevice; // eax
  IUnknown *pProxy; // [rsp+48h] [rbp-28h] BYREF
  __int128 v14; // [rsp+50h] [rbp-20h] BYREF

  switch ( *(_DWORD *)a1 )
  {
    case 1:
      return (unsigned int)ServiceControl::RegisterService();
    case 2:
      return (unsigned int)ServiceControl::UnregisterService();
    case 3:
      return (unsigned int)ServiceControl::StartCollectorService();
    case 4:
      return (unsigned int)ServiceControl::StopCollectorService();
  }
  if ( (unsigned int)(*(_DWORD *)a1 - 7) >= 2 )
    return (unsigned int)-2147418113;
  v3 = 0;
  v5 = CoInitializeEx(0, 0);
  if ( v5 >= 0 )
  {
    v3 = 1;
    pProxy = 0;
    if ( *(_DWORD *)a1 != 7 && *(_DWORD *)a1 != 8 )
    {
      v5 = -2147024809;
      goto LABEL_25;
    }
    pProxy = 0;
    v7 = 0;
    if ( *(_DWORD *)a1 == 8 )
      v7 = 2;
    if ( (_DWORD)v7 )
    {
      v8 = (unsigned int)(v7 - 1);
      if ( (_DWORD)v8 )
      {
        v9 = (unsigned int)(v8 - 1);
        if ( (_DWORD)v9 )
        {
          if ( (_DWORD)v9 == 1 )
            v5 = -2147467263;
          else
            v5 = -2147418113;
LABEL_23:
          if ( v5 < 0 )
          {
LABEL_25:
            if ( pProxy )
              ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
            goto LABEL_27;
          }
LABEL_24:
          v5 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 2u, 3u, 0, 0x800u);
          if ( v5 >= 0 )
          {
            v14 = 0;
            v2 = ((__int64 (__fastcall *)(IUnknown *, __int128 *))pProxy->lpVtbl[1].Release)(pProxy, &v14);
            if ( v2 == -2147024809 )
            {
              wprintf(L"SUCCESS: Expected error from IStandardCollectorService::DestroySession\n");
              v2 = 0;
            }
            if ( pProxy )
              ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
            CoUninitialize();
            return v2;
          }
          goto LABEL_25;
        }
        StandardCollectorServiceForDevice = anonymous_namespace_::CreateStandardCollectorServiceForDevice(
                                              v9,
                                              (LPVOID *)&pProxy);
      }
      else
      {
        StandardCollectorServiceForDevice = anonymous_namespace_::CreateStandardCollectorServiceForRemoteTools(
                                              v8,
                                              v4,
                                              &pProxy);
      }
    }
    else
    {
      StandardCollectorServiceForDevice = anonymous_namespace_::CreateStandardCollectorServiceForVS(
                                            v7,
                                            v4,
                                            v6,
                                            (__int64)&pProxy);
    }
    v5 = StandardCollectorServiceForDevice;
    if ( StandardCollectorServiceForDevice >= 0 )
      goto LABEL_24;
    goto LABEL_23;
  }
LABEL_27:
  if ( v3 )
    CoUninitialize();
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14000356c  mov     rax, rsp
0x14000356f  mov     [rax+8], rbx
0x140003573  mov     [rax+10h], rsi
0x140003577  mov     [rax+18h], rdi
0x14000357b  mov     [rax+20h], r15
0x14000357f  push    rbp
0x140003580  mov     rbp, rsp
0x140003583  sub     rsp, 70h
0x140003587  mov     rax, cs:__security_cookie
0x14000358e  xor     rax, rsp
0x140003591  mov     [rbp+var_10], rax
0x140003595  mov     rsi, rcx
0x140003598  mov     edx, [rcx]
0x14000359a  sub     edx, 1
0x14000359d  jz      loc_14000372E
0x1400035a3  sub     edx, 1
0x1400035a6  jz      loc_140003727
0x1400035ac  sub     edx, 1
0x1400035af  jz      loc_140003720
0x1400035b5  sub     edx, 1
0x1400035b8  jz      loc_140003719
0x1400035be  sub     edx, 3
0x1400035c1  jz      short loc_1400035D2
0x1400035c3  cmp     edx, 1
0x1400035c6  jz      short loc_1400035D2
0x1400035c8  mov     esi, 8000FFFFh
0x1400035cd  jmp     loc_140003735
0x1400035d2  xor     bl, bl
0x1400035d4  xor     edx, edx; dwCoInit
0x1400035d6  xor     ecx, ecx; pvReserved
0x1400035d8  call    cs:__imp_CoInitializeEx
0x1400035de  mov     edi, eax
0x1400035e0  test    eax, eax
0x1400035e2  js      loc_1400036B7
0x1400035e8  mov     bl, 1
0x1400035ea  mov     [rbp+var_30], bl
0x1400035ed  mov     [rbp+pProxy], 0
0x1400035f5  cmp     dword ptr [rsi], 7
0x1400035f8  jz      short loc_140003609
0x1400035fa  cmp     dword ptr [rsi], 8
0x1400035fd  jz      short loc_140003609
0x1400035ff  mov     edi, 80070057h
0x140003604  jmp     loc_1400036A0
0x140003609  mov     [rbp+pProxy], 0
0x140003611  xor     ecx, ecx
0x140003613  lea     r15d, [rcx+2]
0x140003617  cmp     dword ptr [rsi], 8
0x14000361a  cmovz   ecx, r15d
0x14000361e  test    ecx, ecx
0x140003620  jz      short loc_140003655
0x140003622  sub     ecx, 1
0x140003625  jz      short loc_14000364A
0x140003627  sub     ecx, 1
0x14000362a  jz      short loc_14000363F
0x14000362c  cmp     ecx, 1
0x14000362f  jz      short loc_140003638
0x140003631  mov     edi, 8000FFFFh
0x140003636  jmp     short loc_140003664
0x140003638  mov     edi, 80004001h
0x14000363d  jmp     short loc_140003664
0x14000363f  lea     rdx, [rbp+pProxy]
0x140003643  call    _anonymous_namespace___CreateStandardCollectorServiceForDevice
0x140003648  jmp     short loc_14000365E
0x14000364a  lea     r8, [rbp+pProxy]
0x14000364e  call    _anonymous_namespace___CreateStandardCollectorServiceForRemoteTools
0x140003653  jmp     short loc_14000365E
0x140003655  lea     r9, [rbp+pProxy]
0x140003659  call    _anonymous_namespace___CreateStandardCollectorServiceForVS
0x14000365e  mov     edi, eax
0x140003660  test    eax, eax
0x140003662  jns     short loc_140003668
0x140003664  test    edi, edi
0x140003666  js      short loc_1400036A0
0x140003668  mov     [rsp+70h+dwCapabilities], 800h; dwCapabilities
0x140003670  mov     [rsp+70h+pAuthInfo], 0; pAuthInfo
0x140003679  mov     [rsp+70h+dwImpLevel], 3; dwImpLevel
0x140003681  mov     [rsp+70h+dwAuthnLevel], r15d; dwAuthnLevel
0x140003686  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x14000368a  xor     r8d, r8d; dwAuthzSvc
0x14000368d  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x140003690  mov     rcx, [rbp+pProxy]; pProxy
0x140003694  call    cs:__imp_CoSetProxyBlanket
0x14000369a  mov     edi, eax
0x14000369c  test    eax, eax
0x14000369e  jns     short loc_1400036C5
0x1400036a0  mov     rcx, [rbp+pProxy]
0x1400036a4  test    rcx, rcx
0x1400036a7  jz      short loc_1400036B7
0x1400036a9  mov     rax, [rcx]
0x1400036ac  mov     rax, [rax+10h]
0x1400036b0  call    cs:__guard_dispatch_icall_fptr
0x1400036b6  nop
0x1400036b7  test    bl, bl
0x1400036b9  jz      short loc_1400036C1
0x1400036bb  call    cs:__imp_CoUninitialize
0x1400036c1  mov     eax, edi
0x1400036c3  jmp     short loc_140003737
0x1400036c5  xorps   xmm0, xmm0
0x1400036c8  movups  [rbp+var_20], xmm0
0x1400036cc  mov     rcx, [rbp+pProxy]
0x1400036d0  mov     rax, [rcx]
0x1400036d3  lea     rdx, [rbp+var_20]
0x1400036d7  mov     rax, [rax+28h]
0x1400036db  call    cs:__guard_dispatch_icall_fptr
0x1400036e1  mov     esi, eax
0x1400036e3  mov     edi, 80070057h
0x1400036e8  cmp     eax, edi
0x1400036ea  jnz     short loc_1400036FA
0x1400036ec  lea     rcx, aSuccessExpecte; "SUCCESS: Expected error from IStandardC"...
0x1400036f3  call    wprintf
0x1400036f8  xor     esi, esi
0x1400036fa  mov     rcx, [rbp+pProxy]
0x1400036fe  test    rcx, rcx
0x140003701  jz      short loc_140003711
0x140003703  mov     rax, [rcx]
0x140003706  mov     rax, [rax+10h]
0x14000370a  call    cs:__guard_dispatch_icall_fptr
0x140003710  nop
0x140003711  call    cs:__imp_CoUninitialize
0x140003717  jmp     short loc_140003735
0x140003719  call    ?StopCollectorService@ServiceControl@@CAJXZ; ServiceControl::StopCollectorService(void)
0x14000371e  jmp     short loc_140003733
0x140003720  call    ?StartCollectorService@ServiceControl@@CAJXZ; ServiceControl::StartCollectorService(void)
0x140003725  jmp     short loc_140003733
0x140003727  call    ?UnregisterService@ServiceControl@@CAJXZ; ServiceControl::UnregisterService(void)
0x14000372c  jmp     short loc_140003733
0x14000372e  call    ?RegisterService@ServiceControl@@CAJXZ; ServiceControl::RegisterService(void)
0x140003733  mov     esi, eax
0x140003735  mov     eax, esi
0x140003737  mov     rcx, [rbp+var_10]
0x14000373b  xor     rcx, rsp; StackCookie
0x14000373e  call    __security_check_cookie
0x140003743  lea     r11, [rsp+70h+var_s0]
0x140003748  mov     rbx, [r11+10h]
0x14000374c  mov     rsi, [r11+18h]
0x140003750  mov     rdi, [r11+20h]
0x140003754  mov     r15, [r11+28h]
0x140003758  mov     rsp, r11
0x14000375b  pop     rbp
0x14000375c  retn
```
