# GameInputServerManager::CreateServer(void)

- ea: `0x1400017c8`
- end: `0x140001995`
- name: `?CreateServer@GameInputServerManager@@AEAAJXZ`
- size: `461`
- prototype: `__int64 __fastcall(GameInputServerManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000199c`

## callees

- `0x140001008`
- `0x1400017c8`
- `0x140007750`
- `0x140008010`

## pseudocode

```c
__int64 __fastcall GameInputServerManager::CreateServer(GameInputServerManager *this)
{
  __int64 v1; // rax
  __int64 v3; // rdx
  int v4; // ebx
  __int64 v5; // r8
  __int64 v6; // r9
  __int64 v8; // rdi
  __int64 v9; // rcx
  __int64 (__fastcall *v10)(__int64, _QWORD, char *); // r14
  __int64 v11; // r9
  int v12; // [rsp+40h] [rbp-30h] BYREF
  int v13; // [rsp+44h] [rbp-2Ch] BYREF
  __int64 v14; // [rsp+48h] [rbp-28h] BYREF
  __int64 v15; // [rsp+50h] [rbp-20h] BYREF
  int v16; // [rsp+58h] [rbp-18h]
  int v17; // [rsp+5Ch] [rbp-14h]

  v1 = *(_QWORD *)this;
  v14 = 0;
  v15 = 0x46B0C7A8FF66E172LL;
  v16 = -143540582;
  v17 = -557123954;
  v4 = (*(__int64 (__fastcall **)(__int64 *, GUID *, __int64 *))(v1 + 24))(
         &v15,
         &GUID_ff03efb3_9964_4a77_bbf0_2a387f32c83c,
         &v14);
  if ( v4 < 0 )
  {
    if ( (unsigned int)dword_14000E000 > 2 )
    {
      v5 = qword_14000E018;
      v3 = 2048;
      if ( (qword_14000E010 & 0x800) != 0 && (qword_14000E018 & 0x800) == qword_14000E018 )
      {
        v12 = v4;
        v15 = (__int64)"onecore\\xbox\\gameinput\\published\\svc\\gameinputservermanager.cpp";
        v13 = 77;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_14000E010,
          (int)&word_14000A35E,
          qword_14000E018,
          v6,
          (__int64 **)&v15,
          (__int64)&v13,
          (__int64)&v12);
      }
    }
LABEL_6:
    if ( v14 )
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v14 + 16LL))(v14, v3, v5);
    return (unsigned int)v4;
  }
  v8 = v14;
  v9 = *((_QWORD *)this + 1);
  v10 = *(__int64 (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v14 + 24LL);
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    *((_QWORD *)this + 1) = 0;
  }
  v4 = v10(v8, 0, (char *)this + 8);
  if ( v4 < 0 )
  {
    if ( (unsigned int)dword_14000E000 > 2 )
    {
      v5 = qword_14000E018;
      v3 = 2048;
      if ( (qword_14000E010 & 0x800) != 0 && (qword_14000E018 & 0x800) == qword_14000E018 )
      {
        v13 = v4;
        v15 = (__int64)"onecore\\xbox\\gameinput\\published\\svc\\gameinputservermanager.cpp";
        v12 = 80;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_14000E010,
          (int)byte_14000A321,
          qword_14000E018,
          v11,
          (__int64 **)&v15,
          (__int64)&v12,
          (__int64)&v13);
      }
    }
    goto LABEL_6;
  }
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  return 0;
}

```

## disassembly

```asm
0x1400017c8  mov     [rsp-18h+arg_8], rbx
0x1400017cd  mov     [rsp-18h+arg_10], rsi
0x1400017d2  push    rbp
0x1400017d3  push    rdi
0x1400017d4  push    r14
0x1400017d6  mov     rbp, rsp
0x1400017d9  sub     rsp, 70h
0x1400017dd  mov     rax, cs:__security_cookie
0x1400017e4  xor     rax, rsp
0x1400017e7  mov     [rbp+var_10], rax
0x1400017eb  mov     rax, [rcx]
0x1400017ee  lea     r8, [rbp+var_28]
0x1400017f2  mov     rsi, rcx
0x1400017f5  mov     [rbp+var_28], 0
0x1400017fd  mov     dword ptr [rbp+var_20], 0FF66E172h
0x140001804  lea     rdx, _GUID_ff03efb3_9964_4a77_bbf0_2a387f32c83c
0x14000180b  mov     dword ptr [rbp+var_20+4], 46B0C7A8h
0x140001812  lea     rcx, [rbp+var_20]
0x140001816  mov     [rbp+var_18], 0F771BE9Ah
0x14000181d  mov     [rbp+var_14], 0DECAF68Eh
0x140001824  mov     rax, [rax+18h]
0x140001828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000182d  mov     ebx, eax
0x14000182f  test    eax, eax
0x140001831  jns     loc_1400018BD
0x140001837  mov     ecx, cs:dword_14000E000
0x14000183d  cmp     ecx, 2
0x140001840  jbe     short loc_1400018A1
0x140001842  mov     r8, cs:qword_14000E018
0x140001849  mov     edx, 800h
0x14000184e  mov     rcx, cs:qword_14000E010
0x140001855  test    rdx, rcx
0x140001858  jz      short loc_1400018A1
0x14000185a  mov     rax, r8
0x14000185d  and     rax, rdx
0x140001860  cmp     rax, r8
0x140001863  jnz     short loc_1400018A1
0x140001865  lea     rax, aOnecoreXboxGam_4; "onecore\\xbox\\gameinput\\published\\sv"...
0x14000186c  mov     [rbp+var_30], ebx
0x14000186f  mov     [rbp+var_20], rax
0x140001873  lea     rdx, word_14000A35E
0x14000187a  lea     rax, [rbp+var_30]
0x14000187e  mov     [rbp+var_2C], 4Dh ; 'M'
0x140001885  mov     [rsp+70h+var_40], rax
0x14000188a  lea     rax, [rbp+var_2C]
0x14000188e  mov     [rsp+70h+var_48], rax
0x140001893  lea     rax, [rbp+var_20]
0x140001897  mov     [rsp+70h+var_50], rax
0x14000189c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400018a1  mov     rcx, [rbp+var_28]
0x1400018a5  test    rcx, rcx
0x1400018a8  jz      short loc_1400018B6
0x1400018aa  mov     rax, [rcx]
0x1400018ad  mov     rax, [rax+10h]
0x1400018b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400018b6  mov     eax, ebx
0x1400018b8  jmp     loc_140001974
0x1400018bd  mov     rdi, [rbp+var_28]
0x1400018c1  lea     rbx, [rsi+8]
0x1400018c5  mov     rcx, [rbx]
0x1400018c8  mov     rax, [rdi]
0x1400018cb  mov     r14, [rax+18h]
0x1400018cf  test    rcx, rcx
0x1400018d2  jz      short loc_1400018E7
0x1400018d4  mov     rdx, [rcx]
0x1400018d7  mov     rax, [rdx+10h]
0x1400018db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400018e0  mov     qword ptr [rbx], 0
0x1400018e7  mov     r8, rbx
0x1400018ea  xor     edx, edx
0x1400018ec  mov     rcx, rdi
0x1400018ef  mov     rax, r14
0x1400018f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400018f7  mov     ebx, eax
0x1400018f9  test    eax, eax
0x1400018fb  jns     short loc_14000195D
0x1400018fd  mov     ecx, cs:dword_14000E000
0x140001903  cmp     ecx, 2
0x140001906  jbe     short loc_1400018A1
0x140001908  mov     r8, cs:qword_14000E018
0x14000190f  mov     edx, 800h
0x140001914  mov     rcx, cs:qword_14000E010
0x14000191b  test    rdx, rcx
0x14000191e  jz      short loc_1400018A1
0x140001920  mov     rax, r8
0x140001923  and     rax, rdx
0x140001926  cmp     rax, r8
0x140001929  jnz     loc_1400018A1
0x14000192f  lea     rax, aOnecoreXboxGam_4; "onecore\\xbox\\gameinput\\published\\sv"...
0x140001936  mov     [rbp+var_2C], ebx
0x140001939  mov     [rbp+var_20], rax
0x14000193d  lea     rdx, byte_14000A321
0x140001944  lea     rax, [rbp+var_2C]
0x140001948  mov     [rbp+var_30], 50h ; 'P'
0x14000194f  mov     [rsp+70h+var_40], rax
0x140001954  lea     rax, [rbp+var_30]
0x140001958  jmp     loc_14000188E
0x14000195d  mov     rcx, [rbp+var_28]
0x140001961  test    rcx, rcx
0x140001964  jz      short loc_140001972
0x140001966  mov     rax, [rcx]
0x140001969  mov     rax, [rax+10h]
0x14000196d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001972  xor     eax, eax
0x140001974  mov     rcx, [rbp+var_10]
0x140001978  xor     rcx, rsp; StackCookie
0x14000197b  call    __security_check_cookie
0x140001980  lea     r11, [rsp+70h+var_s0]
0x140001985  mov     rbx, [r11+28h]
0x140001989  mov     rsi, [r11+30h]
0x14000198d  mov     rsp, r11
0x140001990  pop     r14
0x140001992  pop     rdi
0x140001993  pop     rbp
0x140001994  retn
```
