# Windows::Networking::UX::Internal::CAccessPointHelper::_AllocAcmNotificationData(ulong,ulong,_GUID const &,_DOT11_SSID const &,ushort const *,bool,ushort const *,wistd::unique_ptr<_L2_NOTIFICATION_DATA,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &)

- ea: `0x180031290`
- end: `0x18003148a`
- name: `?_AllocAcmNotificationData@CAccessPointHelper@Internal@UX@Networking@Windows@@AEAAJKKAEBU_GUID@@AEBU_DOT11_SSID@@PEBG_N2AEAV?$unique_ptr@U_L2_NOTIFICATION_DATA@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@Z`
- size: `506`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180031700`
- `0x18003243c`

## callees

- `0x180004a70`
- `0x1800097b4`
- `0x180009d4c`
- `0x18000de4c`
- `0x18001d4d4`
- `0x18002f290`
- `0x180031290`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003131f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003131f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003146a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003146a`

## string_xrefs

- `0x180031334`: `onecoreuap\net\ux\wlanmediamanager\lib\accesspointhelpers.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::CAccessPointHelper::_AllocAcmNotificationData(
        void *a1,
        int a2,
        int a3,
        _OWORD *a4,
        __int64 a5,
        unsigned __int16 *a6,
        unsigned __int8 a7,
        unsigned __int16 *a8,
        __int64 a9)
{
  unsigned __int16 *v12; // rdi
  __int64 v13; // rbx
  size_t v14; // rsi
  _OWORD *v15; // rax
  char *v17; // r14
  __int64 v18; // rax
  bool v19; // zf
  int v20; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  LPVOID pv; // [rsp+50h] [rbp+8h] BYREF

  pv = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 158, &WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids);
  v12 = a8;
  v13 = 0;
  v14 = 572;
  if ( a7 && a8 )
  {
    v13 = -1;
    do
      ++v13;
    while ( a8[v13] );
    v14 = 2 * v13 + 572;
  }
  v15 = CoTaskMemAlloc(v14 + 40);
  pv = v15;
  if ( v15 )
  {
    v17 = (char *)v15 + 40;
    *v15 = 0;
    v15[1] = 0;
    *((_QWORD *)v15 + 4) = 0;
    *(_DWORD *)v15 = 8;
    *((_DWORD *)v15 + 1) = a2;
    *(_OWORD *)((char *)v15 + 8) = *a4;
    *((_DWORD *)v15 + 6) = v14;
    *((_QWORD *)v15 + 4) = (char *)v15 + 40;
    memset_0((char *)v15 + 40, 0, v14);
    StringCchCopyW((unsigned __int16 *)v17 + 2, 0x100u, a6);
    v18 = a5;
    *(_DWORD *)v17 = 0;
    *((_DWORD *)v17 + 138) = 1;
    *(_OWORD *)(v17 + 516) = *(_OWORD *)v18;
    *(_OWORD *)(v17 + 532) = *(_OWORD *)(v18 + 16);
    *((_DWORD *)v17 + 137) = *(_DWORD *)(v18 + 32);
    LODWORD(v18) = a7 << 31;
    v19 = a7 == 0;
    *((_DWORD *)v17 + 139) = 1;
    *((_DWORD *)v17 + 141) = v18;
    *((_DWORD *)v17 + 140) = a3;
    if ( !v19 && v12 )
      StringCchCopyW((unsigned __int16 *)v17 + 284, v13 + 1, v12);
    wistd::unique_ptr<_L2_NOTIFICATION_DATA,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::operator=(
      a9,
      &pv);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 159, &WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids, 0);
    if ( pv )
      CoTaskMemFree(pv);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6C8,
      (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\accesspointhelpers.cpp",
      (const char *)0x8007000ELL,
      v20);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180031290  mov     [rsp+arg_8], rbx
0x180031295  mov     [rsp+arg_10], rsi
0x18003129a  mov     [rsp+pv], rcx
0x18003129f  push    rdi
0x1800312a0  push    r12
0x1800312a2  push    r13
0x1800312a4  push    r14
0x1800312a6  push    r15; int
0x1800312a8  sub     rsp, 20h
0x1800312ac  mov     r15, r9
0x1800312af  mov     r12d, r8d
0x1800312b2  mov     r13d, edx
0x1800312b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800312bc  lea     rax, WPP_GLOBAL_Control
0x1800312c3  cmp     rcx, rax
0x1800312c6  jz      short loc_1800312E3
0x1800312c8  test    byte ptr [rcx+1Ch], 40h
0x1800312cc  jz      short loc_1800312E3
0x1800312ce  mov     rcx, [rcx+10h]
0x1800312d2  lea     r8, WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids
0x1800312d9  mov     edx, 9Eh
0x1800312de  call    WPP_SF_
0x1800312e3  mov     rdi, [rsp+48h+arg_38]
0x1800312eb  xor     r14d, r14d
0x1800312ee  mov     ebx, r14d
0x1800312f1  mov     esi, 23Ch
0x1800312f6  cmp     [rsp+48h+arg_30], r14b
0x1800312fe  jz      short loc_18003131B
0x180031300  test    rdi, rdi
0x180031303  jz      short loc_18003131B
0x180031305  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180031309  inc     rbx
0x18003130c  cmp     [rdi+rbx*2], r14w
0x180031311  jnz     short loc_180031309
0x180031313  lea     rsi, ds:23Ch[rbx*2]
0x18003131b  lea     rcx, [rsi+28h]; cb
0x18003131f  call    cs:__imp_CoTaskMemAlloc
0x180031325  mov     [rsp+48h+pv], rax
0x18003132a  test    rax, rax
0x18003132d  jnz     short loc_180031354
0x18003132f  mov     rcx, [rsp+48h]; this
0x180031334  lea     r8, aOnecoreuapNetU_0; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18003133b  mov     ebx, 8007000Eh
0x180031340  mov     edx, 6C8h; void *
0x180031345  mov     r9d, ebx; char *
0x180031348  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003134d  mov     eax, ebx
0x18003134f  jmp     loc_180031472
0x180031354  xorps   xmm0, xmm0
0x180031357  lea     r14, [rax+28h]
0x18003135b  movups  xmmword ptr [rax], xmm0
0x18003135e  xor     ecx, ecx
0x180031360  mov     r8, rsi; Size
0x180031363  movups  xmmword ptr [rax+10h], xmm0
0x180031367  mov     [rax+20h], rcx
0x18003136b  xor     edx, edx; Val
0x18003136d  mov     dword ptr [rax], 8
0x180031373  mov     rcx, r14; void *
0x180031376  mov     [rax+4], r13d
0x18003137a  movups  xmm0, xmmword ptr [r15]
0x18003137e  movdqu  xmmword ptr [rax+8], xmm0
0x180031383  mov     [rax+18h], esi
0x180031386  mov     [rax+20h], r14
0x18003138a  call    memset_0
0x18003138f  mov     r8, [rsp+48h+arg_28]; unsigned __int16 *
0x180031394  lea     rcx, [r14+4]; unsigned __int16 *
0x180031398  mov     edx, 100h; unsigned __int64
0x18003139d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800313a2  mov     rax, [rsp+48h+arg_20]
0x1800313a7  mov     ecx, 1
0x1800313ac  mov     dword ptr [r14], 0
0x1800313b3  mov     [r14+228h], ecx
0x1800313ba  movups  xmm0, xmmword ptr [rax]
0x1800313bd  movups  xmmword ptr [r14+204h], xmm0
0x1800313c5  movups  xmm1, xmmword ptr [rax+10h]
0x1800313c9  movups  xmmword ptr [r14+214h], xmm1
0x1800313d1  mov     eax, [rax+20h]
0x1800313d4  mov     [r14+224h], eax
0x1800313db  movzx   eax, [rsp+48h+arg_30]
0x1800313e3  shl     eax, 1Fh
0x1800313e6  cmp     [rsp+48h+arg_30], 0
0x1800313ee  mov     [r14+22Ch], ecx
0x1800313f5  mov     [r14+234h], eax
0x1800313fc  mov     [r14+230h], r12d
0x180031403  jz      short loc_18003141D
0x180031405  test    rdi, rdi
0x180031408  jz      short loc_18003141D
0x18003140a  lea     rdx, [rbx+1]; unsigned __int64
0x18003140e  mov     r8, rdi; unsigned __int16 *
0x180031411  lea     rcx, [r14+238h]; unsigned __int16 *
0x180031418  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003141d  mov     rcx, [rsp+48h+arg_40]
0x180031425  lea     rdx, [rsp+48h+pv]
0x18003142a  call    ??4?$unique_ptr@U_L2_NOTIFICATION_DATA@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<_L2_NOTIFICATION_DATA,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::operator=(wistd::unique_ptr<_L2_NOTIFICATION_DATA,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x18003142f  mov     rcx, cs:WPP_GLOBAL_Control
0x180031436  lea     rax, WPP_GLOBAL_Control
0x18003143d  cmp     rcx, rax
0x180031440  jz      short loc_180031460
0x180031442  test    byte ptr [rcx+1Ch], 40h
0x180031446  jz      short loc_180031460
0x180031448  mov     rcx, [rcx+10h]
0x18003144c  lea     r8, WPP_24b62ade7a69308a26cf9669ced9dc9f_Traceguids
0x180031453  mov     edx, 9Fh
0x180031458  xor     r9d, r9d
0x18003145b  call    WPP_SF_d
0x180031460  mov     rcx, [rsp+48h+pv]; pv
0x180031465  test    rcx, rcx
0x180031468  jz      short loc_180031470
0x18003146a  call    cs:__imp_CoTaskMemFree
0x180031470  xor     eax, eax
0x180031472  mov     rbx, [rsp+48h+arg_8]
0x180031477  mov     rsi, [rsp+48h+arg_10]
0x18003147c  add     rsp, 20h
0x180031480  pop     r15
0x180031482  pop     r14
0x180031484  pop     r13
0x180031486  pop     r12
0x180031488  pop     rdi
0x180031489  retn
```
