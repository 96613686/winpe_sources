# Windows::Networking::UX::Internal::CAccessPointHelper::_AllocSimpleAcmNotificationData(ulong,_GUID const &,wistd::unique_ptr<_L2_NOTIFICATION_DATA,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &)

- ea: `0x18003160c`
- end: `0x1800316f9`
- name: `?_AllocSimpleAcmNotificationData@CAccessPointHelper@Internal@UX@Networking@Windows@@AEAAJKAEBU_GUID@@AEAV?$unique_ptr@U_L2_NOTIFICATION_DATA@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@Z`
- size: `237`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003118c`

## callees

- `0x1800097b4`
- `0x18000de4c`
- `0x18001d4d4`
- `0x18002f290`
- `0x18003160c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031654`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031654`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800316e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800316e8`

## string_xrefs

- `0x180031669`: `onecoreuap\net\ux\wlanmediamanager\lib\accesspointhelpers.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::CAccessPointHelper::_AllocSimpleAcmNotificationData(
        void *a1,
        int a2,
        _OWORD *a3,
        __int64 a4)
{
  _OWORD *v7; // rax
  int v9; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  LPVOID pv; // [rsp+50h] [rbp+8h] BYREF

  pv = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 160, &WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids);
  v7 = CoTaskMemAlloc(0x28u);
  pv = v7;
  if ( v7 )
  {
    *v7 = 0;
    v7[1] = 0;
    *((_QWORD *)v7 + 4) = 0;
    *(_DWORD *)v7 = 8;
    *((_DWORD *)v7 + 1) = a2;
    *(_OWORD *)((char *)v7 + 8) = *a3;
    wistd::unique_ptr<_L2_NOTIFICATION_DATA,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::operator=(
      a4,
      &pv);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 161, &WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids, 0);
    if ( pv )
      CoTaskMemFree(pv);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6EF,
      (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\accesspointhelpers.cpp",
      (const char *)0x8007000ELL,
      v9);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18003160c  mov     [rsp+pv], rcx
0x180031611  push    rbx
0x180031612  push    rbp
0x180031613  push    rsi
0x180031614  push    rdi
0x180031615  sub     rsp, 28h
0x180031619  mov     rbx, r9
0x18003161c  mov     rdi, r8
0x18003161f  mov     esi, edx
0x180031621  mov     rcx, cs:WPP_GLOBAL_Control
0x180031628  lea     rbp, WPP_GLOBAL_Control
0x18003162f  cmp     rcx, rbp
0x180031632  jz      short loc_18003164F
0x180031634  test    byte ptr [rcx+1Ch], 40h
0x180031638  jz      short loc_18003164F
0x18003163a  mov     rcx, [rcx+10h]
0x18003163e  lea     r8, WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids
0x180031645  mov     edx, 0A0h
0x18003164a  call    WPP_SF_
0x18003164f  mov     ecx, 28h ; '('; cb
0x180031654  call    cs:__imp_CoTaskMemAlloc
0x18003165a  mov     [rsp+48h+pv], rax
0x18003165f  test    rax, rax
0x180031662  jnz     short loc_180031686
0x180031664  mov     rcx, [rsp+48h]; this
0x180031669  lea     r8, aOnecoreuapNetU_0; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x180031670  mov     ebx, 8007000Eh
0x180031675  mov     edx, 6EFh; void *
0x18003167a  mov     r9d, ebx; char *
0x18003167d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031682  mov     eax, ebx
0x180031684  jmp     short loc_1800316F0
0x180031686  xorps   xmm0, xmm0
0x180031689  lea     rdx, [rsp+48h+pv]
0x18003168e  movups  xmmword ptr [rax], xmm0
0x180031691  xor     ecx, ecx
0x180031693  movups  xmmword ptr [rax+10h], xmm0
0x180031697  mov     [rax+20h], rcx
0x18003169b  mov     rcx, rbx
0x18003169e  mov     dword ptr [rax], 8
0x1800316a4  mov     [rax+4], esi
0x1800316a7  movups  xmm0, xmmword ptr [rdi]
0x1800316aa  movdqu  xmmword ptr [rax+8], xmm0
0x1800316af  call    ??4?$unique_ptr@U_L2_NOTIFICATION_DATA@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<_L2_NOTIFICATION_DATA,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::operator=(wistd::unique_ptr<_L2_NOTIFICATION_DATA,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x1800316b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800316bb  cmp     rcx, rbp
0x1800316be  jz      short loc_1800316DE
0x1800316c0  test    byte ptr [rcx+1Ch], 40h
0x1800316c4  jz      short loc_1800316DE
0x1800316c6  mov     rcx, [rcx+10h]
0x1800316ca  lea     r8, WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids
0x1800316d1  mov     edx, 0A1h
0x1800316d6  xor     r9d, r9d
0x1800316d9  call    WPP_SF_d
0x1800316de  mov     rcx, [rsp+48h+pv]; pv
0x1800316e3  test    rcx, rcx
0x1800316e6  jz      short loc_1800316EE
0x1800316e8  call    cs:__imp_CoTaskMemFree
0x1800316ee  xor     eax, eax
0x1800316f0  add     rsp, 28h
0x1800316f4  pop     rdi
0x1800316f5  pop     rsi
0x1800316f6  pop     rbp
0x1800316f7  pop     rbx
0x1800316f8  retn
```
