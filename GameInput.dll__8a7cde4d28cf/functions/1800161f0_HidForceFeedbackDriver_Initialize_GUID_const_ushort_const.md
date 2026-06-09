# HidForceFeedbackDriver::Initialize(_GUID const &,ushort const *)

- ea: `0x1800161f0`
- end: `0x180016349`
- name: `?Initialize@HidForceFeedbackDriver@@QEAAJAEBU_GUID@@PEBG@Z`
- size: `345`
- prototype: `__int64 __fastcall(HidForceFeedbackDriver *__hidden this, const struct _GUID *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180018390`

## callees

- `0x180001304`
- `0x1800161f0`
- `0x18004c8e0`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016259`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016259`

## pseudocode

```c
__int64 __fastcall HidForceFeedbackDriver::Initialize(
        HidForceFeedbackDriver *this,
        const struct _GUID *a2,
        const unsigned __int16 *a3)
{
  LPVOID *ppv; // rdi
  __int64 v5; // rcx
  HRESULT Instance; // ebx
  int v9; // r8d
  int v10; // r9d
  __int64 v12; // rax
  __int128 v13; // xmm0
  LPVOID v14; // rcx
  int v15; // eax
  unsigned int v16; // ecx
  HRESULT v17; // [rsp+40h] [rbp-40h] BYREF
  int v18; // [rsp+44h] [rbp-3Ch] BYREF
  const char *v19; // [rsp+48h] [rbp-38h] BYREF
  _QWORD v20[2]; // [rsp+50h] [rbp-30h] BYREF
  __int128 v21; // [rsp+60h] [rbp-20h]

  ppv = (LPVOID *)((char *)this + 16);
  v5 = *((_QWORD *)this + 2);
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    *ppv = 0;
  }
  Instance = CoCreateInstance(
               (const IID *const)(*((_QWORD *)this + 1) + 236LL),
               0,
               1u,
               &IID_IDirectInputEffectDriver,
               ppv);
  if ( Instance >= 0 )
  {
    v12 = *((_QWORD *)this + 1);
    v13 = (__int128)*a2;
    v14 = *ppv;
    v20[0] = 32;
    v21 = v13;
    v20[1] = a3;
    v15 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, __int64, _DWORD, _QWORD *))(*(_QWORD *)v14 + 24LL))(
            v14,
            2048,
            *(unsigned int *)(v12 + 2000),
            1,
            *(_DWORD *)(v12 + 2000),
            v20);
    v16 = 0;
    if ( v15 < 0 )
      return (unsigned int)v15;
    return v16;
  }
  else
  {
    if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
    {
      v17 = Instance;
      v19 = "onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackDriver.cpp";
      v18 = 20;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_180069010,
        (unsigned int)word_18005C40A,
        v9,
        v10,
        (__int64)&v19,
        (__int64)&v18,
        (__int64)&v17);
    }
    return (unsigned int)Instance;
  }
}

```

## disassembly

```asm
0x1800161f0  mov     [rsp-28h+arg_18], rbx
0x1800161f5  push    rbp
0x1800161f6  push    rsi
0x1800161f7  push    rdi
0x1800161f8  push    r14
0x1800161fa  push    r15
0x1800161fc  mov     rbp, rsp
0x1800161ff  sub     rsp, 80h
0x180016206  mov     rax, cs:__security_cookie
0x18001620d  xor     rax, rsp
0x180016210  mov     [rbp+var_10], rax
0x180016214  lea     rdi, [rcx+10h]
0x180016218  mov     rsi, rcx
0x18001621b  mov     rcx, [rdi]
0x18001621e  mov     r15, r8
0x180016221  mov     r14, rdx
0x180016224  test    rcx, rcx
0x180016227  jz      short loc_18001623C
0x180016229  mov     rax, [rcx]
0x18001622c  mov     rax, [rax+10h]
0x180016230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016235  mov     qword ptr [rdi], 0
0x18001623c  mov     rcx, [rsi+8]
0x180016240  lea     r9, IID_IDirectInputEffectDriver; riid
0x180016247  xor     edx, edx; pUnkOuter
0x180016249  mov     [rsp+80h+ppv], rdi; ppv
0x18001624e  add     rcx, 0ECh; rclsid
0x180016255  lea     r8d, [rdx+1]; dwClsContext
0x180016259  call    cs:__imp_CoCreateInstance
0x180016260  nop     dword ptr [rax+rax+00h]
0x180016265  mov     ebx, eax
0x180016267  test    eax, eax
0x180016269  jns     short loc_1800162D4
0x18001626b  mov     ecx, cs:dword_180069000
0x180016271  cmp     ecx, 2
0x180016274  jbe     short loc_1800162D0
0x180016276  mov     rdx, cs:qword_180069018
0x18001627d  mov     rcx, cs:qword_180069010
0x180016284  test    cl, 8
0x180016287  jz      short loc_1800162D0
0x180016289  mov     rax, rdx
0x18001628c  and     eax, 8
0x18001628f  cmp     rax, rdx
0x180016292  jnz     short loc_1800162D0
0x180016294  lea     rax, aOnecoreXboxGam_1; "onecore\\xbox\\gameinput\\feedback\\hid"...
0x18001629b  mov     [rbp+var_40], ebx
0x18001629e  mov     [rbp+var_38], rax
0x1800162a2  lea     rdx, word_18005C40A
0x1800162a9  lea     rax, [rbp+var_40]
0x1800162ad  mov     [rbp+var_3C], 14h
0x1800162b4  mov     [rsp+80h+var_50], rax
0x1800162b9  lea     rax, [rbp+var_3C]
0x1800162bd  mov     [rsp+80h+var_58], rax
0x1800162c2  lea     rax, [rbp+var_38]
0x1800162c6  mov     [rsp+80h+ppv], rax
0x1800162cb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800162d0  mov     eax, ebx
0x1800162d2  jmp     short loc_180016325
0x1800162d4  mov     rax, [rsi+8]
0x1800162d8  lea     rdx, [rbp+var_30]
0x1800162dc  movups  xmm0, xmmword ptr [r14]
0x1800162e0  mov     rcx, [rdi]
0x1800162e3  mov     r9d, 1
0x1800162e9  mov     [rbp+var_30], 20h ; ' '
0x1800162f1  movdqu  [rbp+var_20], xmm0
0x1800162f6  mov     [rbp+var_28], r15
0x1800162fa  mov     r8d, [rax+7D0h]
0x180016301  mov     rax, [rcx]
0x180016304  mov     [rsp+80h+var_58], rdx
0x180016309  mov     edx, 800h
0x18001630e  mov     dword ptr [rsp+80h+ppv], r8d
0x180016313  mov     rax, [rax+18h]
0x180016317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001631c  xor     ecx, ecx
0x18001631e  test    eax, eax
0x180016320  cmovs   ecx, eax
0x180016323  mov     eax, ecx
0x180016325  mov     rcx, [rbp+var_10]
0x180016329  xor     rcx, rsp; StackCookie
0x18001632c  call    __security_check_cookie
0x180016331  mov     rbx, [rsp+80h+arg_18]
0x180016339  add     rsp, 80h
0x180016340  pop     r15
0x180016342  pop     r14
0x180016344  pop     rdi
0x180016345  pop     rsi
0x180016346  pop     rbp
0x180016347  retn
```
