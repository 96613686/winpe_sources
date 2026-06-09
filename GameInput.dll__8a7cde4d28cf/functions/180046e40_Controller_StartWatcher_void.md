# Controller::StartWatcher(void)

- ea: `0x180046e40`
- end: `0x1800470a7`
- name: `?StartWatcher@Controller@@QEAAJXZ`
- size: `615`
- prototype: `__int64 __fastcall(Controller *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800465e0`

## callees

- `0x180001304`
- `0x1800438b0`
- `0x180046e40`
- `0x18004d010`

## string_xrefs

- `0x180046ece`: `onecore\xbox\gameinput\xboxgipservices\Controller.cpp`
- `0x180046f74`: `onecore\xbox\gameinput\xboxgipservices\Controller.cpp`
- `0x180047067`: `onecore\xbox\gameinput\xboxgipservices\Controller.cpp`

## pseudocode

```c
__int64 __fastcall Controller::StartWatcher(Controller *this)
{
  _QWORD *v2; // rsi
  _QWORD *v3; // r14
  int v4; // r8d
  int v5; // r9d
  __int64 v6; // rdi
  unsigned int v7; // ebx
  char *v8; // rdx
  const char **v9; // rcx
  __int64 v11; // rdx
  __int64 v12; // r8
  int v13; // r9d
  int v14; // r15d
  __int64 (__fastcall *v15)(Controller *__hidden, struct Windows::Gaming::Input::IGameController *, struct Windows::System::IUserChangedEventArgs *); // [rsp+40h] [rbp-10h] BYREF
  int v16; // [rsp+48h] [rbp-8h]
  __int64 v17; // [rsp+80h] [rbp+30h] BYREF
  int v18; // [rsp+88h] [rbp+38h] BYREF
  const char *v19; // [rsp+90h] [rbp+40h] BYREF

  if ( *((_QWORD *)this + 9) )
  {
    v16 = 0;
    v15 = Controller::OnUserAssociationChanged;
    Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::Gaming::Input::IGameController *,Windows::System::UserChangedEventArgs *>,Controller,Windows::Gaming::Input::IGameController *,Windows::System::IUserChangedEventArgs *>(
      &v17,
      this,
      &v15);
    v6 = v17;
    if ( !v17 )
    {
      v7 = -2147024882;
      if ( (unsigned int)dword_180069000 <= 2
        || (qword_180069010 & 0x800) == 0
        || (qword_180069018 & 0x800) != qword_180069018 )
      {
        return v7;
      }
      v18 = 110;
      v19 = "onecore\\xbox\\gameinput\\xboxgipservices\\Controller.cpp";
      v8 = byte_1800630DB;
      v9 = &v19;
LABEL_8:
      LODWORD(v17) = v7;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v9,
        (_DWORD)v8,
        v4,
        v5,
        (__int64)&v19,
        (__int64)&v18,
        (__int64)&v17);
      return v7;
    }
    v3 = (_QWORD *)((char *)this + 40);
    v2 = (_QWORD *)((char *)this + 120);
    v14 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(**((_QWORD **)this + 5) + 80LL))(
            *((_QWORD *)this + 5),
            v17,
            (char *)this + 120);
    if ( v14 < 0 )
    {
      if ( (unsigned int)dword_180069000 > 2 )
      {
        v12 = qword_180069018;
        v11 = 2048;
        if ( (qword_180069010 & 0x800) != 0 && (qword_180069018 & 0x800) == qword_180069018 )
        {
          LODWORD(v17) = v14;
          v18 = 113;
          v19 = "onecore\\xbox\\gameinput\\xboxgipservices\\Controller.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (unsigned int)"onecore\\xbox\\gameinput\\xboxgipservices\\Controller.cpp",
            (unsigned int)byte_180063893,
            qword_180069018,
            v13,
            (__int64)&v19,
            (__int64)&v18,
            (__int64)&v17);
        }
      }
      if ( v6 )
        (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v6 + 16LL))(v6, v11, v12);
      return (unsigned int)v14;
    }
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  else
  {
    v2 = (_QWORD *)((char *)this + 120);
    v3 = (_QWORD *)((char *)this + 40);
  }
  if ( *((_QWORD *)this + 4) )
  {
    v7 = (*(__int64 (__fastcall **)(_QWORD, Controller *))(**((_QWORD **)this + 7) + 160LL))(
           *((_QWORD *)this + 7),
           this);
    if ( (v7 & 0x80000000) != 0 )
    {
      if ( *v2 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v3 + 88LL))(*v3);
        *v2 = 0;
      }
      if ( (unsigned int)dword_180069000 <= 2
        || (qword_180069010 & 0x800) == 0
        || (qword_180069018 & 0x800) != qword_180069018 )
      {
        return v7;
      }
      v18 = 127;
      v9 = (const char **)"onecore\\xbox\\gameinput\\xboxgipservices\\Controller.cpp";
      v19 = "onecore\\xbox\\gameinput\\xboxgipservices\\Controller.cpp";
      v8 = byte_180062F1D;
      goto LABEL_8;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180046e40  mov     [rsp-28h+arg_18], rbx
0x180046e45  push    rbp
0x180046e46  push    rsi
0x180046e47  push    rdi
0x180046e48  push    r14
0x180046e4a  push    r15
0x180046e4c  mov     rbp, rsp
0x180046e4f  sub     rsp, 50h
0x180046e53  cmp     qword ptr [rcx+48h], 0
0x180046e58  mov     rbx, rcx
0x180046e5b  jnz     short loc_180046E6A
0x180046e5d  lea     rsi, [rcx+78h]
0x180046e61  lea     r14, [rcx+28h]
0x180046e65  jmp     loc_180046FD4
0x180046e6a  lea     rax, ?OnUserAssociationChanged@Controller@@AEAAJPEAUIGameController@Input@Gaming@Windows@@PEAUIUserChangedEventArgs@System@5@@Z; Controller::OnUserAssociationChanged(Windows::Gaming::Input::IGameController *,Windows::System::IUserChangedEventArgs *)
0x180046e71  mov     [rbp+var_8], 0
0x180046e78  mov     [rbp+var_10], rax
0x180046e7c  lea     r8, [rbp+var_10]
0x180046e80  mov     eax, [rbp+var_4]
0x180046e83  lea     rcx, [rbp+arg_0]
0x180046e87  mov     rdx, rbx
0x180046e8a  mov     [rbp+var_4], eax
0x180046e8d  call    ??$Callback@U?$ITypedEventHandler@PEAUIGameController@Input@Gaming@Windows@@PEAVUserChangedEventArgs@System@4@@Foundation@Windows@@VController@@PEAUIGameController@Input@Gaming@3@PEAUIUserChangedEventArgs@System@3@@WRL@Microsoft@@YA?AV?$ComPtr@U?$ITypedEventHandler@PEAUIGameController@Input@Gaming@Windows@@PEAVUserChangedEventArgs@System@4@@Foundation@Windows@@@01@PEAVController@@P83@EAAJPEAUIGameController@Input@Gaming@Windows@@PEAUIUserChangedEventArgs@System@7@@Z@Z; Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::Gaming::Input::IGameController *,Windows::System::UserChangedEventArgs *>,Controller,Windows::Gaming::Input::IGameController *,Windows::System::IUserChangedEventArgs *>(Controller *,long (Controller::*)(Windows::Gaming::Input::IGameController *,Windows::System::IUserChangedEventArgs *))
0x180046e92  mov     rdi, [rbp+arg_0]
0x180046e96  test    rdi, rdi
0x180046e99  jnz     short loc_180046F11
0x180046e9b  mov     eax, cs:dword_180069000
0x180046ea1  mov     ebx, 8007000Eh
0x180046ea6  cmp     eax, 2
0x180046ea9  jbe     short loc_180046F0A
0x180046eab  mov     rcx, cs:qword_180069018
0x180046eb2  mov     edx, 800h
0x180046eb7  mov     rax, cs:qword_180069010
0x180046ebe  test    rdx, rax
0x180046ec1  jz      short loc_180046F0A
0x180046ec3  mov     rax, rcx
0x180046ec6  and     rax, rdx
0x180046ec9  cmp     rax, rcx
0x180046ecc  jnz     short loc_180046F0A
0x180046ece  lea     rcx, aOnecoreXboxGam_37; "onecore\\xbox\\gameinput\\xboxgipservic"...
0x180046ed5  mov     [rbp+arg_8], 6Eh ; 'n'
0x180046edc  mov     [rbp+arg_10], rcx
0x180046ee0  lea     rdx, byte_1800630DB
0x180046ee7  lea     rcx, [rbp+arg_0]
0x180046eeb  mov     [rsp+50h+var_20], rcx
0x180046ef0  lea     rcx, [rbp+arg_8]
0x180046ef4  mov     [rsp+50h+var_28], rcx
0x180046ef9  lea     rcx, [rbp+arg_10]
0x180046efd  mov     [rsp+50h+var_30], rcx
0x180046f02  mov     dword ptr [rbp+arg_0], ebx
0x180046f05  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180046f0a  mov     eax, ebx
0x180046f0c  jmp     loc_180047092
0x180046f11  lea     r14, [rbx+28h]
0x180046f15  mov     rdx, rdi
0x180046f18  mov     rcx, [r14]
0x180046f1b  lea     rsi, [rbx+78h]
0x180046f1f  mov     r8, rsi
0x180046f22  mov     rax, [rcx]
0x180046f25  mov     rax, [rax+50h]
0x180046f29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046f2e  mov     r15d, eax
0x180046f31  test    eax, eax
0x180046f33  jns     loc_180046FC0
0x180046f39  mov     ecx, cs:dword_180069000
0x180046f3f  cmp     ecx, 2
0x180046f42  jbe     short loc_180046FA4
0x180046f44  mov     r8, cs:qword_180069018
0x180046f4b  mov     edx, 800h
0x180046f50  mov     rcx, cs:qword_180069010
0x180046f57  test    rdx, rcx
0x180046f5a  jz      short loc_180046FA4
0x180046f5c  mov     rax, r8
0x180046f5f  and     rax, rdx
0x180046f62  cmp     rax, r8
0x180046f65  jnz     short loc_180046FA4
0x180046f67  lea     rax, [rbp+arg_0]
0x180046f6b  mov     dword ptr [rbp+arg_0], r15d
0x180046f6f  mov     [rsp+50h+var_20], rax
0x180046f74  lea     rcx, aOnecoreXboxGam_37; "onecore\\xbox\\gameinput\\xboxgipservic"...
0x180046f7b  lea     rax, [rbp+arg_8]
0x180046f7f  mov     [rbp+arg_8], 71h ; 'q'
0x180046f86  mov     [rsp+50h+var_28], rax
0x180046f8b  lea     rdx, byte_180063893
0x180046f92  lea     rax, [rbp+arg_10]
0x180046f96  mov     [rbp+arg_10], rcx
0x180046f9a  mov     [rsp+50h+var_30], rax
0x180046f9f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180046fa4  test    rdi, rdi
0x180046fa7  jz      short loc_180046FB8
0x180046fa9  mov     rax, [rdi]
0x180046fac  mov     rcx, rdi
0x180046faf  mov     rax, [rax+10h]
0x180046fb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046fb8  mov     eax, r15d
0x180046fbb  jmp     loc_180047092
0x180046fc0  test    rdi, rdi
0x180046fc3  jz      short loc_180046FD4
0x180046fc5  mov     rax, [rdi]
0x180046fc8  mov     rcx, rdi
0x180046fcb  mov     rax, [rax+10h]
0x180046fcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046fd4  cmp     qword ptr [rbx+20h], 0
0x180046fd9  jz      loc_180047090
0x180046fdf  mov     rcx, [rbx+38h]
0x180046fe3  mov     rdx, rbx
0x180046fe6  mov     rax, [rcx]
0x180046fe9  mov     rax, [rax+0A0h]
0x180046ff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046ff5  mov     ebx, eax
0x180046ff7  test    eax, eax
0x180046ff9  jns     loc_180047090
0x180046fff  mov     rdx, [rsi]
0x180047002  test    rdx, rdx
0x180047005  jz      short loc_18004701D
0x180047007  mov     rcx, [r14]
0x18004700a  mov     r8, [rcx]
0x18004700d  mov     rax, [r8+58h]
0x180047011  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047016  mov     qword ptr [rsi], 0
0x18004701d  mov     eax, cs:dword_180069000
0x180047023  cmp     eax, 2
0x180047026  jbe     loc_180046F0A
0x18004702c  mov     rcx, cs:qword_180069018
0x180047033  mov     edx, 800h
0x180047038  mov     rax, cs:qword_180069010
0x18004703f  test    rdx, rax
0x180047042  jz      loc_180046F0A
0x180047048  mov     rax, rcx
0x18004704b  and     rax, rdx
0x18004704e  cmp     rax, rcx
0x180047051  jnz     loc_180046F0A
0x180047057  lea     rax, [rbp+arg_0]
0x18004705b  mov     [rbp+arg_8], 7Fh
0x180047062  mov     [rsp+50h+var_20], rax
0x180047067  lea     rcx, aOnecoreXboxGam_37; "onecore\\xbox\\gameinput\\xboxgipservic"...
0x18004706e  lea     rax, [rbp+arg_8]
0x180047072  mov     [rbp+arg_10], rcx
0x180047076  mov     [rsp+50h+var_28], rax
0x18004707b  lea     rdx, byte_180062F1D
0x180047082  lea     rax, [rbp+arg_10]
0x180047086  mov     [rsp+50h+var_30], rax
0x18004708b  jmp     loc_180046F02
0x180047090  xor     eax, eax
0x180047092  mov     rbx, [rsp+50h+arg_18]
0x18004709a  add     rsp, 50h
0x18004709e  pop     r15
0x1800470a0  pop     r14
0x1800470a2  pop     rdi
0x1800470a3  pop     rsi
0x1800470a4  pop     rbp
0x1800470a5  retn
```
