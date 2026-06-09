# RadioInstance::_UpdateUIEnabled(void)

- ea: `0x180016940`
- end: `0x180016a15`
- name: `?_UpdateUIEnabled@RadioInstance@@AEAAXXZ`
- size: `213`
- prototype: `void __fastcall(RadioInstance *__hidden this)`
- caller_count: `8`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180011408`
- `0x180013c00`
- `0x180013ea0`
- `0x180013fd0`
- `0x180015630`
- `0x180015840`
- `0x180015a70`
- `0x180015b80`

## callees

- `0x180006eec`
- `0x180007568`
- `0x1800080fc`
- `0x18000b814`
- `0x180016940`

## pseudocode

```c
void __fastcall RadioInstance::_UpdateUIEnabled(RadioInstance *this)
{
  char v1; // al
  const enum SliderPosition *v3; // rcx
  __int64 v4; // r8
  const struct _GUID *v5; // r8
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 *v9; // [rsp+60h] [rbp-20h] BYREF
  const wchar_t *v10; // [rsp+68h] [rbp-18h] BYREF
  __int64 v11; // [rsp+70h] [rbp-10h] BYREF
  int v12; // [rsp+90h] [rbp+10h] BYREF
  int v13; // [rsp+98h] [rbp+18h] BYREF
  const wchar_t *v14; // [rsp+A0h] [rbp+20h] BYREF
  const wchar_t *v15; // [rsp+A8h] [rbp+28h] BYREF

  v1 = 0;
  if ( (*((_BYTE *)this + 88) & 6) != 0
    || *((_DWORD *)this + 23)
    || (v3 = (RadioInstance *)((char *)this + 100), *(_DWORD *)v3 == 2) )
  {
    v3 = (RadioInstance *)((char *)this + 100);
  }
  else
  {
    v1 = 1;
  }
  *((_BYTE *)this + 105) = v1;
  if ( (unsigned int)dword_180037050 > 4 )
  {
    v14 = (const wchar_t *)RMToString(v3);
    v12 = *(_DWORD *)(v4 + 92);
    v15 = (const wchar_t *)RMToString((const enum _DEVICE_RADIO_STATE *)(v4 + 88));
    v13 = v5[6].Data4[1];
    v9 = *(__int64 **)v5[7].Data4;
    v10 = (const wchar_t *)RmGuidToMediaTypeString(v5 + 8);
    v11 = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v6,
      (unsigned __int8 *)byte_18002DEF9,
      v7,
      v8,
      &v11,
      &v10,
      &v9,
      (__int64)&v13,
      &v15,
      (__int64)&v12,
      &v14);
  }
}

```

## disassembly

```asm
0x180016940  push    rbp
0x180016942  mov     rbp, rsp
0x180016945  sub     rsp, 80h
0x18001694c  xor     eax, eax
0x18001694e  mov     r8, rcx
0x180016951  test    byte ptr [rcx+58h], 6
0x180016955  jnz     short loc_180016969
0x180016957  cmp     [rcx+5Ch], eax
0x18001695a  ja      short loc_180016969
0x18001695c  add     rcx, 64h ; 'd'
0x180016960  cmp     dword ptr [rcx], 2
0x180016963  jz      short loc_180016969
0x180016965  mov     al, 1
0x180016967  jmp     short loc_18001696D
0x180016969  lea     rcx, [r8+64h]; enum SliderPosition *
0x18001696d  mov     [r8+69h], al
0x180016971  mov     eax, cs:dword_180037050
0x180016977  cmp     eax, 4
0x18001697a  jbe     loc_180016A0C
0x180016980  call    ?RMToString@@YAPEBDAEBW4SliderPosition@@@Z; RMToString(SliderPosition const &)
0x180016985  mov     [rbp+arg_10], rax
0x180016989  lea     rcx, [r8+58h]; enum _DEVICE_RADIO_STATE *
0x18001698d  mov     eax, [r8+5Ch]
0x180016991  mov     [rbp+arg_0], eax
0x180016994  call    ?RMToString@@YAPEBDAEBW4_DEVICE_RADIO_STATE@@@Z; RMToString(_DEVICE_RADIO_STATE const &)
0x180016999  mov     [rbp+arg_18], rax
0x18001699d  lea     rcx, [r8+80h]; struct _GUID *
0x1800169a4  movzx   eax, byte ptr [r8+69h]
0x1800169a9  mov     [rbp+arg_8], eax
0x1800169ac  mov     rax, [r8+78h]
0x1800169b0  mov     [rbp+var_20], rax
0x1800169b4  call    ?RmGuidToMediaTypeString@@YAPEBDAEBU_GUID@@@Z; RmGuidToMediaTypeString(_GUID const &)
0x1800169b9  mov     [rbp+var_18], rax
0x1800169bd  lea     rdx, byte_18002DEF9
0x1800169c4  lea     rax, [rbp+arg_10]
0x1800169c8  mov     [rbp+var_10], rcx
0x1800169cc  mov     [rsp+80h+var_30], rax
0x1800169d1  lea     rax, [rbp+arg_0]
0x1800169d5  mov     [rsp+80h+var_38], rax
0x1800169da  lea     rax, [rbp+arg_18]
0x1800169de  mov     [rsp+80h+var_40], rax
0x1800169e3  lea     rax, [rbp+arg_8]
0x1800169e7  mov     [rsp+80h+var_48], rax
0x1800169ec  lea     rax, [rbp+var_20]
0x1800169f0  mov     [rsp+80h+var_50], rax
0x1800169f5  lea     rax, [rbp+var_18]
0x1800169f9  mov     [rsp+80h+var_58], rax
0x1800169fe  lea     rax, [rbp+var_10]
0x180016a02  mov     [rsp+80h+var_60], rax
0x180016a07  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@U2@U4@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@464@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180016a0c  add     rsp, 80h
0x180016a13  pop     rbp
0x180016a14  retn
```
