# TextMessage::CreateInstance(Windows::Devices::Sms::ISmsMessageBase *,ulong,TextMessage * *)

- ea: `0x18000a1c0`
- end: `0x18000a2c5`
- name: `?CreateInstance@TextMessage@@SAJPEAUISmsMessageBase@Sms@Devices@Windows@@KPEAPEAV1@@Z`
- size: `261`
- prototype: `__int64 __fastcall(__int64 (__fastcall ***)(struct Windows::Devices::Sms::ISmsMessageBase *, GUID *, __int64 *), __int64, struct TextMessage **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180007d50`

## callees

- `0x180001730`
- `0x18000a1c0`
- `0x18000a2ec`
- `0x18000a328`
- `0x18000aa27`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall TextMessage::CreateInstance(
        __int64 (__fastcall ***a1)(struct Windows::Devices::Sms::ISmsMessageBase *, GUID *, __int64 *),
        __int64 a2,
        struct TextMessage **a3)
{
  _DWORD *v5; // rax
  __int64 v6; // r8
  _DWORD *v7; // rbx
  struct ATL::CAtlModule *v8; // rcx
  int v9; // edi
  void (__fastcall **v10)(void *); // rax

  *a3 = 0;
  v5 = operator new(0x90u);
  v7 = v5;
  if ( v5 )
  {
    memset_0(v5, 0, 0x90u);
    v7[34] = -1;
    *((_QWORD *)v7 + 3) = v7 + 10;
    *((_QWORD *)v7 + 4) = v7 + 10;
    *((_QWORD *)v7 + 11) = v7 + 26;
    *((_QWORD *)v7 + 12) = v7 + 26;
    *((_QWORD *)v7 + 7) = v7 + 18;
    *((_QWORD *)v7 + 8) = v7 + 18;
    v8 = ATL::_pAtlModule;
    *(_QWORD *)v7 = &ATL::CComObject<TextMessage>::`vftable';
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v8 + 8LL))(v8);
    (**(void (__fastcall ***)(void *))v7)(v7);
    v9 = TextMessage::_Initialize((TextMessage *)v7, a1, 0);
    v10 = *(void (__fastcall ***)(void *))v7;
    if ( v9 >= 0 )
    {
      (*v10)(v7);
      *a3 = (struct TextMessage *)v7;
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v7 + 8LL))(v7);
      return 0;
    }
    v10[1](v7);
  }
  else
  {
    v9 = -2147024882;
  }
  Log_HREvent_6((unsigned int)v9, 1, v6, 18);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000a1c0  mov     [rsp+arg_8], rbx
0x18000a1c5  mov     [rsp+arg_18], rsi
0x18000a1ca  push    rdi
0x18000a1cb  sub     rsp, 30h
0x18000a1cf  mov     rdi, rcx
0x18000a1d2  mov     qword ptr [r8], 0
0x18000a1d9  mov     ecx, 90h; Size
0x18000a1de  mov     rsi, r8
0x18000a1e1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a1e6  mov     rbx, rax
0x18000a1e9  test    rax, rax
0x18000a1ec  jz      loc_18000A29E
0x18000a1f2  xor     edx, edx; Val
0x18000a1f4  mov     r8d, 90h; Size
0x18000a1fa  mov     rcx, rax; void *
0x18000a1fd  call    memset_0
0x18000a202  lea     rcx, [rbx+28h]
0x18000a206  mov     dword ptr [rbx+88h], 0FFFFFFFFh
0x18000a210  mov     [rbx+18h], rcx
0x18000a214  lea     rax, [rbx+68h]
0x18000a218  mov     [rbx+20h], rcx
0x18000a21c  lea     rcx, [rbx+48h]
0x18000a220  mov     [rbx+58h], rax
0x18000a224  mov     [rbx+60h], rax
0x18000a228  lea     rax, ??_7?$CComObject@VTextMessage@@@ATL@@6B@; const ATL::CComObject<TextMessage>::`vftable'
0x18000a22f  mov     [rbx+38h], rcx
0x18000a233  mov     [rbx+40h], rcx
0x18000a237  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000a23e  mov     [rbx], rax
0x18000a241  mov     rax, [rcx]
0x18000a244  mov     rax, [rax+8]
0x18000a248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a24d  mov     rax, [rbx]
0x18000a250  mov     rcx, rbx
0x18000a253  mov     rax, [rax]
0x18000a256  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a25b  xor     r8d, r8d; unsigned int
0x18000a25e  mov     rdx, rdi; struct Windows::Devices::Sms::ISmsMessageBase *
0x18000a261  mov     rcx, rbx; this
0x18000a264  call    ?_Initialize@TextMessage@@AEAAJPEAUISmsMessageBase@Sms@Devices@Windows@@K@Z; TextMessage::_Initialize(Windows::Devices::Sms::ISmsMessageBase *,ulong)
0x18000a269  mov     edi, eax
0x18000a26b  test    eax, eax
0x18000a26d  mov     rax, [rbx]
0x18000a270  mov     rcx, rbx
0x18000a273  jns     short loc_18000A280
0x18000a275  mov     rax, [rax+8]
0x18000a279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a27e  jmp     short loc_18000A2A3
0x18000a280  mov     rax, [rax]
0x18000a283  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a288  mov     [rsi], rbx
0x18000a28b  mov     rcx, rbx
0x18000a28e  mov     rax, [rbx]
0x18000a291  mov     rax, [rax+8]
0x18000a295  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a29a  xor     eax, eax
0x18000a29c  jmp     short loc_18000A2B5
0x18000a29e  mov     edi, 8007000Eh
0x18000a2a3  mov     edx, 1
0x18000a2a8  mov     ecx, edi
0x18000a2aa  lea     r9d, [rdx+11h]
0x18000a2ae  call    Log_HREvent_6
0x18000a2b3  mov     eax, edi
0x18000a2b5  mov     rbx, [rsp+38h+arg_8]
0x18000a2ba  mov     rsi, [rsp+38h+arg_18]
0x18000a2bf  add     rsp, 30h
0x18000a2c3  pop     rdi
0x18000a2c4  retn
```
