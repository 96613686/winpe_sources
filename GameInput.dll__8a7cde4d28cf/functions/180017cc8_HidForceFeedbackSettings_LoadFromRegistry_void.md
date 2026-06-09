# HidForceFeedbackSettings::LoadFromRegistry(void)

- ea: `0x180017cc8`
- end: `0x180017ddd`
- name: `?LoadFromRegistry@HidForceFeedbackSettings@@QEAAJXZ`
- size: `277`
- prototype: `__int64 __fastcall(HidForceFeedbackSettings *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180012d70`
- `0x180018390`

## callees

- `0x180001304`
- `0x180017088`
- `0x180017cc8`
- `0x18004c8e0`

## import_xrefs

- `ntdll!swprintf_s` at `0x180017d14`
- `ntdll!swprintf_s` at `0x180017d14`

## pseudocode

```c
__int64 __fastcall HidForceFeedbackSettings::LoadFromRegistry(HidForceFeedbackSettings *this)
{
  __int64 v1; // r9
  int v3; // ebx
  __int64 v4; // r8
  __int64 v5; // r9
  int v7; // [rsp+20h] [rbp-60h]
  int v8; // [rsp+40h] [rbp-40h] BYREF
  int v9; // [rsp+44h] [rbp-3Ch] BYREF
  const char *v10; // [rsp+48h] [rbp-38h] BYREF
  wchar_t Buffer[8]; // [rsp+50h] [rbp-30h] BYREF
  __int128 v12; // [rsp+60h] [rbp-20h]
  int v13; // [rsp+70h] [rbp-10h]

  v1 = *((unsigned int *)this + 1);
  v13 = 0;
  v7 = *((_DWORD *)this + 2);
  *(_OWORD *)Buffer = 0;
  v12 = 0;
  swprintf_s(Buffer, 0x12u, L"VID_%04X&PID_%04X", v1, v7);
  if ( (int)HidForceFeedbackSettings::LoadFromRegistry(this, HKEY_CURRENT_USER, Buffer) >= 0 )
    return 0;
  v3 = HidForceFeedbackSettings::LoadFromRegistry(this, HKEY_LOCAL_MACHINE, Buffer);
  if ( v3 >= 0 )
    return 0;
  if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
  {
    v8 = v3;
    v10 = "onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackSettings.cpp";
    v9 = 67;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      qword_180069010,
      (unsigned __int8 *)byte_18005C33D,
      v4,
      v5,
      (__int64 **)&v10,
      (__int64)&v9,
      (__int64)&v8);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180017cc8  mov     [rsp-8+arg_8], rbx
0x180017ccd  push    rbp
0x180017cce  mov     rbp, rsp
0x180017cd1  sub     rsp, 80h
0x180017cd8  mov     rax, cs:__security_cookie
0x180017cdf  xor     rax, rsp
0x180017ce2  mov     [rbp+var_8], rax
0x180017ce6  mov     r9d, [rcx+4]
0x180017cea  lea     r8, aVid04xPid04x; "VID_%04X&PID_%04X"
0x180017cf1  xor     eax, eax
0x180017cf3  xorps   xmm0, xmm0
0x180017cf6  mov     [rbp+var_10], eax
0x180017cf9  mov     rbx, rcx
0x180017cfc  mov     eax, [rcx+8]
0x180017cff  mov     edx, 12h; BufferCount
0x180017d04  lea     rcx, [rbp+Buffer]; Buffer
0x180017d08  mov     dword ptr [rsp+80h+var_60], eax
0x180017d0c  movups  xmmword ptr [rbp+Buffer], xmm0
0x180017d10  movups  [rbp+var_20], xmm0
0x180017d14  call    cs:__imp_swprintf_s
0x180017d1b  nop     dword ptr [rax+rax+00h]
0x180017d20  lea     r8, [rbp+Buffer]; lpSubKey
0x180017d24  mov     rdx, 0FFFFFFFF80000001h; hKey
0x180017d2b  mov     rcx, rbx; this
0x180017d2e  call    ?LoadFromRegistry@HidForceFeedbackSettings@@AEAAJPEAUHKEY__@@PEBG@Z; HidForceFeedbackSettings::LoadFromRegistry(HKEY__ *,ushort const *)
0x180017d33  test    eax, eax
0x180017d35  jns     loc_180017DBD
0x180017d3b  lea     r8, [rbp+Buffer]; lpSubKey
0x180017d3f  mov     rdx, 0FFFFFFFF80000002h; hKey
0x180017d46  mov     rcx, rbx; this
0x180017d49  call    ?LoadFromRegistry@HidForceFeedbackSettings@@AEAAJPEAUHKEY__@@PEBG@Z; HidForceFeedbackSettings::LoadFromRegistry(HKEY__ *,ushort const *)
0x180017d4e  mov     ebx, eax
0x180017d50  test    eax, eax
0x180017d52  jns     short loc_180017DBD
0x180017d54  mov     ecx, cs:dword_180069000
0x180017d5a  cmp     ecx, 2
0x180017d5d  jbe     short loc_180017DB9
0x180017d5f  mov     rdx, cs:qword_180069018
0x180017d66  mov     rcx, cs:qword_180069010
0x180017d6d  test    cl, 8
0x180017d70  jz      short loc_180017DB9
0x180017d72  mov     rax, rdx
0x180017d75  and     eax, 8
0x180017d78  cmp     rax, rdx
0x180017d7b  jnz     short loc_180017DB9
0x180017d7d  lea     rax, aOnecoreXboxGam_52; "onecore\\xbox\\gameinput\\feedback\\hid"...
0x180017d84  mov     [rbp+var_40], ebx
0x180017d87  mov     [rbp+var_38], rax
0x180017d8b  lea     rdx, byte_18005C33D
0x180017d92  lea     rax, [rbp+var_40]
0x180017d96  mov     [rbp+var_3C], 43h ; 'C'
0x180017d9d  mov     [rsp+80h+var_50], rax
0x180017da2  lea     rax, [rbp+var_3C]
0x180017da6  mov     [rsp+80h+var_58], rax
0x180017dab  lea     rax, [rbp+var_38]
0x180017daf  mov     [rsp+80h+var_60], rax
0x180017db4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180017db9  mov     eax, ebx
0x180017dbb  jmp     short loc_180017DBF
0x180017dbd  xor     eax, eax
0x180017dbf  mov     rcx, [rbp+var_8]
0x180017dc3  xor     rcx, rsp; StackCookie
0x180017dc6  call    __security_check_cookie
0x180017dcb  mov     rbx, [rsp+80h+arg_8]
0x180017dd3  add     rsp, 80h
0x180017dda  pop     rbp
0x180017ddb  retn
```
