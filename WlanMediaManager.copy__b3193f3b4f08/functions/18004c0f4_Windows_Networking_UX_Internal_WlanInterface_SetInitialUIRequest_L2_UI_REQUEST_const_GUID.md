# Windows::Networking::UX::Internal::WlanInterface::_SetInitialUIRequest(_L2_UI_REQUEST const &,_GUID)

- ea: `0x18004c0f4`
- end: `0x18004c244`
- name: `?_SetInitialUIRequest@WlanInterface@Internal@UX@Networking@Windows@@IEAAJAEBU_L2_UI_REQUEST@@U_GUID@@@Z`
- size: `336`
- prototype: `int(Windows::Networking::UX::Internal::WlanInterface *__hidden this, const struct _L2_UI_REQUEST *, struct _GUID *__struct_ptr)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800508d0`

## callees

- `0x1800097b4`
- `0x18000de4c`
- `0x18001d4d4`
- `0x18003a070`
- `0x180048ee4`
- `0x18004c0f4`
- `0x180051728`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004c1d5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004c1d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c1a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c229`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c1a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c229`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Networking::UX::Internal::WlanInterface::_SetInitialUIRequest(
        struct _GUID *this,
        const struct _L2_UI_REQUEST *a2,
        struct _GUID *a3)
{
  int v6; // ebx
  void *v7; // rcx
  void *v9; // rcx
  struct _FILETIME SystemTimeAsFileTime; // [rsp+20h] [rbp-20h] BYREF
  LPVOID *p_pv; // [rsp+28h] [rbp-18h] BYREF
  struct _L2_UI_REQUEST *v12; // [rsp+30h] [rbp-10h] BYREF
  char v13; // [rsp+38h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  LPVOID pv; // [rsp+78h] [rbp+38h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 247, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids);
  pv = 0;
  p_pv = &pv;
  v12 = 0;
  v13 = 1;
  v6 = Windows::Networking::UX::Internal::WlanInterface::_CopyUIRequest(a2, &v12);
  wil::details::out_param_t<wistd::unique_ptr<_L2_UI_RESPONSE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_L2_UI_RESPONSE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( v6 >= 0 )
  {
    wistd::unique_ptr<_L2_UI_REQUEST,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::swap(
      &this[46],
      &pv);
    this[45] = *a3;
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    *(struct _FILETIME *)this[46].Data4 = SystemTimeAsFileTime;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 248, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids, 0);
    v9 = pv;
    pv = 0;
    if ( v9 )
      CoTaskMemFree(v9);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC8E,
      (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlaninterface.cpp",
      (const char *)(unsigned int)v6,
      SystemTimeAsFileTime.dwLowDateTime);
    v7 = pv;
    pv = 0;
    if ( v7 )
      CoTaskMemFree(v7);
    return (unsigned int)v6;
  }
}

```

## disassembly

```asm
0x18004c0f4  mov     [rsp-18h+arg_0], rbx
0x18004c0f9  mov     [rsp-18h+arg_8], rsi
0x18004c0fe  push    rbp
0x18004c0ff  push    rdi
0x18004c100  push    r15
0x18004c102  mov     rbp, rsp
0x18004c105  sub     rsp, 40h
0x18004c109  mov     rsi, r8
0x18004c10c  mov     rbx, rdx
0x18004c10f  mov     rdi, rcx
0x18004c112  lea     r15, WPP_GLOBAL_Control
0x18004c119  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c120  cmp     rcx, r15
0x18004c123  jz      short loc_18004C140
0x18004c125  test    byte ptr [rcx+1Ch], 40h
0x18004c129  jz      short loc_18004C140
0x18004c12b  mov     edx, 0F7h
0x18004c130  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x18004c137  mov     rcx, [rcx+10h]
0x18004c13b  call    WPP_SF_
0x18004c140  mov     [rbp+pv], 0
0x18004c148  lea     rax, [rbp+pv]
0x18004c14c  mov     [rbp+var_18], rax
0x18004c150  mov     [rbp+var_10], 0
0x18004c158  mov     [rbp+var_8], 1
0x18004c15c  lea     rdx, [rbp+var_10]; struct _L2_UI_REQUEST **
0x18004c160  mov     rcx, rbx; Src
0x18004c163  call    ?_CopyUIRequest@WlanInterface@Internal@UX@Networking@Windows@@KAJAEBU_L2_UI_REQUEST@@PEAPEAU6@@Z; Windows::Networking::UX::Internal::WlanInterface::_CopyUIRequest(_L2_UI_REQUEST const &,_L2_UI_REQUEST * *)
0x18004c168  mov     ebx, eax
0x18004c16a  lea     rcx, [rbp+var_18]
0x18004c16e  call    ??1?$out_param_t@V?$unique_ptr@U_L2_UI_RESPONSE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_L2_UI_RESPONSE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_L2_UI_RESPONSE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18004c173  test    ebx, ebx
0x18004c175  jns     short loc_18004C1AE
0x18004c177  mov     rcx, [rbp+18h]; this
0x18004c17b  mov     r9d, ebx; char *
0x18004c17e  lea     r8, aOnecoreuapNetU_20; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18004c185  mov     edx, 0C8Eh; void *
0x18004c18a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004c18f  nop
0x18004c190  mov     rcx, [rbp+pv]; pv
0x18004c194  mov     [rbp+pv], 0
0x18004c19c  test    rcx, rcx
0x18004c19f  jz      short loc_18004C1A7
0x18004c1a1  call    cs:__imp_CoTaskMemFree
0x18004c1a7  mov     eax, ebx
0x18004c1a9  jmp     loc_18004C231
0x18004c1ae  lea     rcx, [rdi+2E0h]
0x18004c1b5  lea     rdx, [rbp+pv]
0x18004c1b9  call    ?swap@?$unique_ptr@U_L2_UI_REQUEST@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXAEAV12@@Z; wistd::unique_ptr<_L2_UI_REQUEST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::swap(wistd::unique_ptr<_L2_UI_REQUEST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &)
0x18004c1be  movaps  xmm0, xmmword ptr [rsi]
0x18004c1c1  movdqu  xmmword ptr [rdi+2D0h], xmm0
0x18004c1c9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18004c1d1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18004c1d5  call    cs:__imp_GetSystemTimeAsFileTime
0x18004c1db  mov     eax, [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18004c1de  mov     [rdi+2E8h], eax
0x18004c1e4  mov     eax, [rbp+SystemTimeAsFileTime.dwHighDateTime]
0x18004c1e7  mov     [rdi+2ECh], eax
0x18004c1ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c1f4  cmp     rcx, r15
0x18004c1f7  jz      short loc_18004C218
0x18004c1f9  test    byte ptr [rcx+1Ch], 40h
0x18004c1fd  jz      short loc_18004C218
0x18004c1ff  mov     edx, 0F8h
0x18004c204  xor     r9d, r9d
0x18004c207  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x18004c20e  mov     rcx, [rcx+10h]
0x18004c212  call    WPP_SF_d
0x18004c217  nop
0x18004c218  mov     rcx, [rbp+pv]; pv
0x18004c21c  mov     [rbp+pv], 0
0x18004c224  test    rcx, rcx
0x18004c227  jz      short loc_18004C22F
0x18004c229  call    cs:__imp_CoTaskMemFree
0x18004c22f  xor     eax, eax
0x18004c231  mov     rbx, [rsp+40h+arg_0]
0x18004c236  mov     rsi, [rsp+40h+arg_8]
0x18004c23b  add     rsp, 40h
0x18004c23f  pop     r15
0x18004c241  pop     rdi
0x18004c242  pop     rbp
0x18004c243  retn
```
