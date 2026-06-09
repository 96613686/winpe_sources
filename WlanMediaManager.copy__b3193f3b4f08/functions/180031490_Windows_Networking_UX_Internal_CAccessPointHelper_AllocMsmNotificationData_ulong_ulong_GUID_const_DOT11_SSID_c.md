# Windows::Networking::UX::Internal::CAccessPointHelper::_AllocMsmNotificationData(ulong,ulong,_GUID const &,_DOT11_SSID const &,ushort const *,wistd::unique_ptr<_L2_NOTIFICATION_DATA,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &)

- ea: `0x180031490`
- end: `0x180031605`
- name: `?_AllocMsmNotificationData@CAccessPointHelper@Internal@UX@Networking@Windows@@AEAAJKKAEBU_GUID@@AEBU_DOT11_SSID@@PEBGAEAV?$unique_ptr@U_L2_NOTIFICATION_DATA@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@Z`
- size: `373`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180031700`
- `0x180032868`

## callees

- `0x180004a70`
- `0x1800097b4`
- `0x180009d4c`
- `0x18000de4c`
- `0x18001d4d4`
- `0x18002f290`
- `0x180031490`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800314e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800314e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800315ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800315ea`

## string_xrefs

- `0x1800314f7`: `onecoreuap\net\ux\wlanmediamanager\lib\accesspointhelpers.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::CAccessPointHelper::_AllocMsmNotificationData(
        void *a1,
        int a2,
        int a3,
        _OWORD *a4,
        __int64 a5,
        unsigned __int16 *a6,
        __int64 a7)
{
  _OWORD *v10; // rax
  char *v12; // rbx
  __int64 v13; // rax
  __int64 v14; // rcx
  int v15; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPVOID pv; // [rsp+40h] [rbp+8h] BYREF

  pv = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 162, &WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids);
  v10 = CoTaskMemAlloc(0x26Cu);
  pv = v10;
  if ( v10 )
  {
    v12 = (char *)v10 + 40;
    *v10 = 0;
    v10[1] = 0;
    *((_QWORD *)v10 + 4) = 0;
    *(_DWORD *)v10 = 16;
    *((_DWORD *)v10 + 1) = a2;
    *(_OWORD *)((char *)v10 + 8) = *a4;
    *((_DWORD *)v10 + 6) = 580;
    *((_QWORD *)v10 + 4) = (char *)v10 + 40;
    memset_0((char *)v10 + 40, 0, 0x244u);
    StringCchCopyW((unsigned __int16 *)v12 + 2, 0x100u, a6);
    v13 = a5;
    *(_DWORD *)v12 = 0;
    *((_DWORD *)v12 + 138) = 1;
    *(_OWORD *)(v12 + 516) = *(_OWORD *)v13;
    *(_OWORD *)(v12 + 532) = *(_OWORD *)(v13 + 16);
    LODWORD(v13) = *(_DWORD *)(v13 + 32);
    *((_DWORD *)v12 + 141) = 1;
    v14 = a7;
    *((_DWORD *)v12 + 137) = v13;
    *((_DWORD *)v12 + 144) = a3;
    wistd::unique_ptr<_L2_NOTIFICATION_DATA,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::operator=(
      v14,
      &pv);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 163, &WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids, 0);
    if ( pv )
      CoTaskMemFree(pv);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x70B,
      (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\accesspointhelpers.cpp",
      (const char *)0x8007000ELL,
      v15);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180031490  mov     [rsp+arg_8], rbx
0x180031495  mov     [rsp+arg_10], rbp
0x18003149a  mov     [rsp+pv], rcx
0x18003149f  push    rsi
0x1800314a0  push    rdi
0x1800314a1  push    r14; int
0x1800314a3  sub     rsp, 20h
0x1800314a7  mov     rdi, r9
0x1800314aa  mov     esi, r8d
0x1800314ad  mov     ebp, edx
0x1800314af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800314b6  lea     r14, WPP_GLOBAL_Control
0x1800314bd  cmp     rcx, r14
0x1800314c0  jz      short loc_1800314DD
0x1800314c2  test    byte ptr [rcx+1Ch], 40h
0x1800314c6  jz      short loc_1800314DD
0x1800314c8  mov     rcx, [rcx+10h]
0x1800314cc  lea     r8, WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids
0x1800314d3  mov     edx, 0A2h
0x1800314d8  call    WPP_SF_
0x1800314dd  mov     ecx, 26Ch; cb
0x1800314e2  call    cs:__imp_CoTaskMemAlloc
0x1800314e8  mov     [rsp+38h+pv], rax
0x1800314ed  test    rax, rax
0x1800314f0  jnz     short loc_180031517
0x1800314f2  mov     rcx, [rsp+38h]; this
0x1800314f7  lea     r8, aOnecoreuapNetU_0; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x1800314fe  mov     ebx, 8007000Eh
0x180031503  mov     edx, 70Bh; void *
0x180031508  mov     r9d, ebx; char *
0x18003150b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031510  mov     eax, ebx
0x180031512  jmp     loc_1800315F2
0x180031517  xorps   xmm0, xmm0
0x18003151a  lea     rbx, [rax+28h]
0x18003151e  movups  xmmword ptr [rax], xmm0
0x180031521  xor     ecx, ecx
0x180031523  mov     r8d, 244h; Size
0x180031529  movups  xmmword ptr [rax+10h], xmm0
0x18003152d  mov     [rax+20h], rcx
0x180031531  xor     edx, edx; Val
0x180031533  mov     dword ptr [rax], 10h
0x180031539  mov     rcx, rbx; void *
0x18003153c  mov     [rax+4], ebp
0x18003153f  movups  xmm0, xmmword ptr [rdi]
0x180031542  movdqu  xmmword ptr [rax+8], xmm0
0x180031547  mov     [rax+18h], r8d
0x18003154b  mov     [rax+20h], rbx
0x18003154f  call    memset_0
0x180031554  mov     r8, [rsp+38h+arg_28]; unsigned __int16 *
0x180031559  lea     rcx, [rbx+4]; unsigned __int16 *
0x18003155d  mov     edx, 100h; unsigned __int64
0x180031562  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180031567  mov     rax, [rsp+38h+arg_20]
0x18003156c  lea     rdx, [rsp+38h+pv]
0x180031571  mov     dword ptr [rbx], 0
0x180031577  mov     ecx, 1
0x18003157c  mov     [rbx+228h], ecx
0x180031582  movups  xmm0, xmmword ptr [rax]
0x180031585  movups  xmmword ptr [rbx+204h], xmm0
0x18003158c  movups  xmm1, xmmword ptr [rax+10h]
0x180031590  movups  xmmword ptr [rbx+214h], xmm1
0x180031597  mov     eax, [rax+20h]
0x18003159a  mov     [rbx+234h], ecx
0x1800315a0  mov     rcx, [rsp+38h+arg_30]
0x1800315a5  mov     [rbx+224h], eax
0x1800315ab  mov     [rbx+240h], esi
0x1800315b1  call    ??4?$unique_ptr@U_L2_NOTIFICATION_DATA@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<_L2_NOTIFICATION_DATA,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::operator=(wistd::unique_ptr<_L2_NOTIFICATION_DATA,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x1800315b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800315bd  cmp     rcx, r14
0x1800315c0  jz      short loc_1800315E0
0x1800315c2  test    byte ptr [rcx+1Ch], 40h
0x1800315c6  jz      short loc_1800315E0
0x1800315c8  mov     rcx, [rcx+10h]
0x1800315cc  lea     r8, WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids
0x1800315d3  mov     edx, 0A3h
0x1800315d8  xor     r9d, r9d
0x1800315db  call    WPP_SF_d
0x1800315e0  mov     rcx, [rsp+38h+pv]; pv
0x1800315e5  test    rcx, rcx
0x1800315e8  jz      short loc_1800315F0
0x1800315ea  call    cs:__imp_CoTaskMemFree
0x1800315f0  xor     eax, eax
0x1800315f2  mov     rbx, [rsp+38h+arg_8]
0x1800315f7  mov     rbp, [rsp+38h+arg_10]
0x1800315fc  add     rsp, 20h
0x180031600  pop     r14
0x180031602  pop     rdi
0x180031603  pop     rsi
0x180031604  retn
```
