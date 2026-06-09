# UlAiStartTrackingAddressInformation

- ea: `0x1400cb4c4`
- end: `0x1400cb6ab`
- name: `UlAiStartTrackingAddressInformation`
- size: `487`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400cb0d8`
- `0x1400cb234`

## callees

- `0x14009f1d4`
- `0x1400cb4c4`
- `0x1401c3f58`
- `0x1401da5a4`

## import_xrefs

- `NETIO!NotifyUnicastIpAddressChange` at `0x1400cb5c7`
- `NETIO!NotifyUnicastIpAddressChange` at `0x1400cb5c7`
- `NETIO!NsiDeregisterChangeNotification` at `0x1400cb63c`
- `NETIO!NsiDeregisterChangeNotification` at `0x1400cb65d`
- `NETIO!NsiDeregisterChangeNotification` at `0x1400cb63c`
- `NETIO!NsiDeregisterChangeNotification` at `0x1400cb65d`
- `NETIO!CancelMibChangeNotify2` at `0x1400cb672`
- `NETIO!CancelMibChangeNotify2` at `0x1400cb672`
- `NETIO!NsiRegisterChangeNotification` at `0x1400cb53e`
- `NETIO!NsiRegisterChangeNotification` at `0x1400cb588`
- `NETIO!NsiRegisterChangeNotification` at `0x1400cb53e`
- `NETIO!NsiRegisterChangeNotification` at `0x1400cb588`

## pseudocode

```c
__int64 UlAiStartTrackingAddressInformation()
{
  NTSTATUS v0; // ebx
  HANDLE NotificationHandle; // [rsp+60h] [rbp+30h] BYREF

  NotificationHandle = 0;
  if ( SBYTE2(xmmword_1401A2CA0) < 0 )
    WPP_SF_(1047, 16, WPP_8a82f71bae7e3fbe145cef66ca25cf13_Traceguids);
  if ( (unsigned __int8)UxPodIsCurrentRoot() )
  {
    v0 = 0;
    if ( UlAiNlIpv4NotificationHandle
      || (v0 = NsiRegisterChangeNotification(&NPI_MS_IPV4_MODULEID, 7, UlpAiNlChangeCallback), v0 >= 0) )
    {
      if ( UlAiNlIpv6NotificationHandle
        || (v0 = NsiRegisterChangeNotification(&NPI_MS_IPV6_MODULEID, 7, UlpAiNlChangeCallback), v0 >= 0) )
      {
        if ( !UlAiIpChangeNotificationHandle
          && (v0 = NotifyUnicastIpAddressChange(0, UlpAiIpAddressChangeCallback, 0, 1u, &NotificationHandle), v0 < 0)
          || NotificationHandle
          && !_InterlockedCompareExchange64(
                (volatile signed __int64 *)&UlAiIpChangeNotificationHandle,
                (signed __int64)NotificationHandle,
                0) )
        {
          NotificationHandle = 0;
        }
      }
    }
  }
  else
  {
    v0 = -1073741637;
  }
  if ( NotificationHandle )
    CancelMibChangeNotify2(NotificationHandle);
  if ( SBYTE2(xmmword_1401A2CA0) < 0 )
    WPP_SF_d(1047, 17, WPP_8a82f71bae7e3fbe145cef66ca25cf13_Traceguids, (unsigned int)v0);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x1400cb4c4  push    rbp
0x1400cb4c6  push    rbx
0x1400cb4c7  push    rdi
0x1400cb4c8  mov     rbp, rsp
0x1400cb4cb  sub     rsp, 30h
0x1400cb4cf  xor     edi, edi
0x1400cb4d1  mov     [rbp+arg_0], rdi
0x1400cb4d5  mov     [rbp+arg_8], rdi
0x1400cb4d9  mov     [rbp+arg_10], rdi
0x1400cb4dd  cmp     byte ptr cs:xmmword_1401A2CA0+2, dil
0x1400cb4e4  jge     short loc_1400CB4FA
0x1400cb4e6  lea     edx, [rdi+10h]
0x1400cb4e9  mov     ecx, 417h
0x1400cb4ee  lea     r8, WPP_8a82f71bae7e3fbe145cef66ca25cf13_Traceguids
0x1400cb4f5  call    WPP_SF_
0x1400cb4fa  call    UxPodIsCurrentRoot
0x1400cb4ff  test    al, al
0x1400cb501  jnz     short loc_1400CB50D
0x1400cb503  mov     ebx, 0C00000BBh
0x1400cb508  jmp     loc_1400CB627
0x1400cb50d  mov     rax, cs:UlAiNlIpv4NotificationHandle
0x1400cb514  mov     ebx, edi
0x1400cb516  test    rax, rax
0x1400cb519  jnz     short loc_1400CB559
0x1400cb51b  xor     r9d, r9d
0x1400cb51e  lea     rax, [rbp+arg_0]
0x1400cb522  mov     [rsp+30h+var_8], rax
0x1400cb527  lea     r8, UlpAiNlChangeCallback
0x1400cb52e  lea     rcx, NPI_MS_IPV4_MODULEID
0x1400cb535  mov     [rsp+30h+NotificationHandle], rdi
0x1400cb53a  lea     edx, [r9+7]
0x1400cb53e  call    cs:__imp_NsiRegisterChangeNotification
0x1400cb545  nop     dword ptr [rax+rax+00h]
0x1400cb54a  mov     ebx, eax
0x1400cb54c  test    eax, eax
0x1400cb54e  jns     short loc_1400CB559
0x1400cb550  mov     [rbp+arg_0], rdi
0x1400cb554  jmp     loc_1400CB648
0x1400cb559  mov     rax, cs:UlAiNlIpv6NotificationHandle
0x1400cb560  test    rax, rax
0x1400cb563  jnz     short loc_1400CB5A3
0x1400cb565  xor     r9d, r9d
0x1400cb568  lea     rax, [rbp+arg_8]
0x1400cb56c  mov     [rsp+30h+var_8], rax
0x1400cb571  lea     r8, UlpAiNlChangeCallback
0x1400cb578  lea     rcx, NPI_MS_IPV6_MODULEID
0x1400cb57f  mov     [rsp+30h+NotificationHandle], rdi
0x1400cb584  lea     edx, [r9+7]
0x1400cb588  call    cs:__imp_NsiRegisterChangeNotification
0x1400cb58f  nop     dword ptr [rax+rax+00h]
0x1400cb594  mov     ebx, eax
0x1400cb596  test    eax, eax
0x1400cb598  jns     short loc_1400CB5A3
0x1400cb59a  mov     [rbp+arg_8], rdi
0x1400cb59e  jmp     loc_1400CB627
0x1400cb5a3  mov     rax, cs:UlAiIpChangeNotificationHandle
0x1400cb5aa  test    rax, rax
0x1400cb5ad  jnz     short loc_1400CB5D9
0x1400cb5af  lea     rax, [rbp+arg_10]
0x1400cb5b3  xor     ecx, ecx; Family
0x1400cb5b5  mov     r9b, 1; InitialNotification
0x1400cb5b8  mov     [rsp+30h+NotificationHandle], rax; NotificationHandle
0x1400cb5bd  xor     r8d, r8d; CallerContext
0x1400cb5c0  lea     rdx, UlpAiIpAddressChangeCallback; Callback
0x1400cb5c7  call    cs:__imp_NotifyUnicastIpAddressChange
0x1400cb5ce  nop     dword ptr [rax+rax+00h]
0x1400cb5d3  mov     ebx, eax
0x1400cb5d5  test    eax, eax
0x1400cb5d7  js      short loc_1400CB623
0x1400cb5d9  mov     r8, [rbp+arg_0]
0x1400cb5dd  test    r8, r8
0x1400cb5e0  jz      short loc_1400CB5F3
0x1400cb5e2  xor     eax, eax
0x1400cb5e4  lock cmpxchg cs:UlAiNlIpv4NotificationHandle, r8
0x1400cb5ed  jnz     short loc_1400CB5F3
0x1400cb5ef  mov     [rbp+arg_0], rdi
0x1400cb5f3  mov     r8, [rbp+arg_8]
0x1400cb5f7  test    r8, r8
0x1400cb5fa  jz      short loc_1400CB60D
0x1400cb5fc  xor     eax, eax
0x1400cb5fe  lock cmpxchg cs:UlAiNlIpv6NotificationHandle, r8
0x1400cb607  jnz     short loc_1400CB60D
0x1400cb609  mov     [rbp+arg_8], rdi
0x1400cb60d  mov     rcx, [rbp+arg_10]
0x1400cb611  test    rcx, rcx
0x1400cb614  jz      short loc_1400CB627
0x1400cb616  xor     eax, eax
0x1400cb618  lock cmpxchg cs:UlAiIpChangeNotificationHandle, rcx
0x1400cb621  jnz     short loc_1400CB627
0x1400cb623  mov     [rbp+arg_10], rdi
0x1400cb627  mov     r8, [rbp+arg_0]
0x1400cb62b  test    r8, r8
0x1400cb62e  jz      short loc_1400CB648
0x1400cb630  mov     edx, 7
0x1400cb635  lea     rcx, NPI_MS_IPV4_MODULEID
0x1400cb63c  call    cs:__imp_NsiDeregisterChangeNotification
0x1400cb643  nop     dword ptr [rax+rax+00h]
0x1400cb648  mov     r8, [rbp+arg_8]
0x1400cb64c  test    r8, r8
0x1400cb64f  jz      short loc_1400CB669
0x1400cb651  mov     edx, 7
0x1400cb656  lea     rcx, NPI_MS_IPV6_MODULEID
0x1400cb65d  call    cs:__imp_NsiDeregisterChangeNotification
0x1400cb664  nop     dword ptr [rax+rax+00h]
0x1400cb669  mov     rcx, [rbp+arg_10]; NotificationHandle
0x1400cb66d  test    rcx, rcx
0x1400cb670  jz      short loc_1400CB67E
0x1400cb672  call    cs:__imp_CancelMibChangeNotify2
0x1400cb679  nop     dword ptr [rax+rax+00h]
0x1400cb67e  cmp     byte ptr cs:xmmword_1401A2CA0+2, dil
0x1400cb685  jge     short loc_1400CB6A0
0x1400cb687  mov     edx, 11h
0x1400cb68c  lea     r8, WPP_8a82f71bae7e3fbe145cef66ca25cf13_Traceguids
0x1400cb693  mov     ecx, 417h
0x1400cb698  mov     r9d, ebx
0x1400cb69b  call    WPP_SF_d
0x1400cb6a0  mov     eax, ebx
0x1400cb6a2  add     rsp, 30h
0x1400cb6a6  pop     rdi
0x1400cb6a7  pop     rbx
0x1400cb6a8  pop     rbp
0x1400cb6a9  retn
```
