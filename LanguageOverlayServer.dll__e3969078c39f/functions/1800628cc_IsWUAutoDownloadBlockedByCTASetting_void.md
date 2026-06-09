# _IsWUAutoDownloadBlockedByCTASetting(void)

- ea: `0x1800628cc`
- end: `0x180062a7a`
- name: `?_IsWUAutoDownloadBlockedByCTASetting@@YA_NXZ`
- size: `430`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180061e88`
- `0x180062194`

## callees

- `0x18000a024`
- `0x180012a98`
- `0x1800628cc`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180062901`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180062901`

## string_xrefs

- `0x1800629cb`: `onecore\base\languageoverlay\common\policyutils.cpp`
- `0x180062a53`: `onecore\base\languageoverlay\common\policyutils.cpp`
- `0x180062a67`: `onecore\base\languageoverlay\common\policyutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
bool _IsWUAutoDownloadBlockedByCTASetting(void)
{
  HRESULT v0; // eax
  LPVOID v1; // rbx
  __int64 (__fastcall *v2)(LPVOID, const wchar_t *, _QWORD **); // rdi
  _QWORD *v3; // rcx
  int v4; // eax
  int v5; // eax
  wil::details::in1diag3 *v6; // rcx
  __int64 v7; // rdx
  bool result; // al
  int v9; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int v11; // [rsp+50h] [rbp+8h] BYREF
  int v12; // [rsp+58h] [rbp+10h] BYREF
  _QWORD *v13; // [rsp+60h] [rbp+18h] BYREF
  LPVOID v14; // [rsp+68h] [rbp+20h] BYREF

  v13 = 0;
  v14 = 0;
  v0 = CoCreateInstance(
         &GUID_b91d5831_b1bd_4608_8198_d72e155020f7,
         0,
         4u,
         &GUID_c57692f8_8f5f_47cb_9381_34329b40285a,
         &v14);
  try
  {
    if ( v0 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB1,
        (unsigned int)"onecore\\base\\languageoverlay\\common\\policyutils.cpp",
        (const char *)(unsigned int)v0,
        v9);
    v1 = v14;
    v2 = *(__int64 (__fastcall **)(LPVOID, const wchar_t *, _QWORD **))(*(_QWORD *)v14 + 40LL);
    v3 = v13;
    v13 = 0;
    if ( v3 )
      (*(void (__fastcall **)(_QWORD *, _QWORD))(*v3 + 16LL))(v3, *v3);
    v4 = v2(v1, L"Language", &v13);
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB3,
        (unsigned int)"onecore\\base\\languageoverlay\\common\\policyutils.cpp",
        (const char *)(unsigned int)v4,
        v9);
    v11 = 0;
    v5 = (*(__int64 (__fastcall **)(_QWORD *, int *))(*v13 + 456LL))(v13, &v11);
    v6 = retaddr;
    if ( v5 < 0 )
    {
      v7 = 183;
LABEL_11:
      wil::details::in1diag3::_Log_Hr(
        v6,
        (void *)v7,
        (unsigned int)"onecore\\base\\languageoverlay\\common\\policyutils.cpp",
        (const char *)(unsigned int)v5,
        v9);
      goto LABEL_18;
    }
    if ( v11 != 1 )
    {
LABEL_18:
      if ( v13 )
        (*(void (__fastcall **)(_QWORD *))(*v13 + 16LL))(v13);
      if ( v14 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v14 + 16LL))(v14);
      return 0;
    }
    v12 = 1;
    v5 = (*(__int64 (__fastcall **)(_QWORD *, int *))(*v13 + 320LL))(v13, &v12);
    v6 = retaddr;
    if ( v5 < 0 )
    {
      v7 = 187;
      goto LABEL_11;
    }
    if ( v12 )
      goto LABEL_18;
    if ( v13 )
      (*(void (__fastcall **)(_QWORD *))(*v13 + 16LL))(v13);
    if ( v14 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v14 + 16LL))(v14);
    result = 1;
  }
  catch ( ... )
  {
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800628cc  mov     r11, rsp
0x1800628cf  push    rbx
0x1800628d0  push    rdi
0x1800628d1  sub     rsp, 38h
0x1800628d5  mov     qword ptr [r11+18h], 0
0x1800628dd  mov     qword ptr [r11+20h], 0
0x1800628e5  lea     rax, [r11+20h]
0x1800628e9  mov     [r11-28h], rax
0x1800628ed  lea     r9, _GUID_c57692f8_8f5f_47cb_9381_34329b40285a; riid
0x1800628f4  xor     edx, edx; pUnkOuter
0x1800628f6  lea     r8d, [rdx+4]; dwClsContext
0x1800628fa  lea     rcx, _GUID_b91d5831_b1bd_4608_8198_d72e155020f7; rclsid
0x180062901  call    cs:__imp_CoCreateInstance
0x180062907  mov     rcx, [rsp+48h]; this
0x18006290c  test    eax, eax
0x18006290e  js      loc_180062A50
0x180062914  mov     rbx, [rsp+48h+arg_18]
0x180062919  mov     rax, [rbx]
0x18006291c  mov     rdi, [rax+28h]
0x180062920  mov     rcx, [rsp+48h+arg_10]
0x180062925  mov     [rsp+48h+arg_10], 0
0x18006292e  test    rcx, rcx
0x180062931  jz      short loc_180062940
0x180062933  mov     rdx, [rcx]
0x180062936  mov     rax, [rdx+10h]
0x18006293a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006293f  nop
0x180062940  lea     r8, [rsp+48h+arg_10]
0x180062945  lea     rdx, aLanguage; "Language"
0x18006294c  mov     rcx, rbx
0x18006294f  mov     rax, rdi
0x180062952  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062957  mov     rcx, [rsp+48h]; this
0x18006295c  test    eax, eax
0x18006295e  js      loc_180062A64
0x180062964  mov     [rsp+48h+arg_0], 0
0x18006296c  mov     rcx, [rsp+48h+arg_10]
0x180062971  mov     rax, [rcx]
0x180062974  lea     rdx, [rsp+48h+arg_0]
0x180062979  mov     rax, [rax+1C8h]
0x180062980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062985  mov     rcx, [rsp+48h]
0x18006298a  test    eax, eax
0x18006298c  jns     short loc_180062995
0x18006298e  mov     edx, 0B7h
0x180062993  jmp     short loc_1800629CB
0x180062995  cmp     [rsp+48h+arg_0], 1
0x18006299a  jnz     short loc_180062A15
0x18006299c  mov     [rsp+48h+arg_8], 1
0x1800629a4  mov     rcx, [rsp+48h+arg_10]
0x1800629a9  mov     rax, [rcx]
0x1800629ac  lea     rdx, [rsp+48h+arg_8]
0x1800629b1  mov     rax, [rax+140h]
0x1800629b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800629bd  mov     rcx, [rsp+48h]; this
0x1800629c2  test    eax, eax
0x1800629c4  jns     short loc_1800629DC
0x1800629c6  mov     edx, 0BBh; void *
0x1800629cb  lea     r8, aOnecoreBaseLan_24; "onecore\\base\\languageoverlay\\common"...
0x1800629d2  mov     r9d, eax; char *
0x1800629d5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800629da  jmp     short loc_180062A15
0x1800629dc  cmp     [rsp+48h+arg_8], 0
0x1800629e1  jnz     short loc_180062A15
0x1800629e3  mov     rcx, [rsp+48h+arg_10]
0x1800629e8  test    rcx, rcx
0x1800629eb  jz      short loc_1800629FA
0x1800629ed  mov     rax, [rcx]
0x1800629f0  mov     rax, [rax+10h]
0x1800629f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800629f9  nop
0x1800629fa  mov     rcx, [rsp+48h+arg_18]
0x1800629ff  test    rcx, rcx
0x180062a02  jz      short loc_180062A11
0x180062a04  mov     rdx, [rcx]
0x180062a07  mov     rax, [rdx+10h]
0x180062a0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062a10  nop
0x180062a11  mov     al, 1
0x180062a13  jmp     short loc_180062A49
0x180062a15  mov     rcx, [rsp+48h+arg_10]
0x180062a1a  test    rcx, rcx
0x180062a1d  jz      short loc_180062A2C
0x180062a1f  mov     rax, [rcx]
0x180062a22  mov     rax, [rax+10h]
0x180062a26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062a2b  nop
0x180062a2c  mov     rcx, [rsp+48h+arg_18]
0x180062a31  test    rcx, rcx
0x180062a34  jz      short loc_180062A43
0x180062a36  mov     rax, [rcx]
0x180062a39  mov     rax, [rax+10h]
0x180062a3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062a42  nop
0x180062a43  xor     al, al
0x180062a45  jmp     short loc_180062A49
0x180062a47  xor     al, al
0x180062a49  add     rsp, 38h
0x180062a4d  pop     rdi
0x180062a4e  pop     rbx
0x180062a4f  retn
0x180062a50  mov     r9d, eax; char *
0x180062a53  lea     r8, aOnecoreBaseLan_24; "onecore\\base\\languageoverlay\\common"...
0x180062a5a  mov     edx, 0B1h; void *
0x180062a5f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180062a64  mov     r9d, eax; char *
0x180062a67  lea     r8, aOnecoreBaseLan_24; "onecore\\base\\languageoverlay\\common"...
0x180062a6e  mov     edx, 0B3h; void *
0x180062a73  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
