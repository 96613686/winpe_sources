# Microsoft::WRL::Details::RuntimeClassBaseT<2>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerCustomConsent,IHandlerAccessChange>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerCustomConsent,IHandlerAccessChange> *,_GUID const &,void * *)

- ea: `0x180002990`
- end: `0x180002a2c`
- name: `??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIHandlerCustomConsent@@UIHandlerAccessChange@@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$01@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIHandlerCustomConsent@@UIHandlerAccessChange@@@123@AEBU_GUID@@PEAPEAX@Z`
- size: `156`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002920`
- `0x180004320`

## callees

- `0x180002990`
- `0x18000302c`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassBaseT<2>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerCustomConsent,IHandlerAccessChange>>(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  int CanCastTo; // ebx

  *a3 = 0;
  if ( *a2 )
  {
    if ( *a2 == -1923871779
      && a2[1] == *(_DWORD *)&GUID_8d540bdd_316f_4204_ac18_799fffd29f12.Data2
      && a2[2] == *(_DWORD *)GUID_8d540bdd_316f_4204_ac18_799fffd29f12.Data4
      && a2[3] == *(_DWORD *)&GUID_8d540bdd_316f_4204_ac18_799fffd29f12.Data4[4] )
    {
      *a3 = a1;
      CanCastTo = 0;
LABEL_12:
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 8LL))(*a3);
      return (unsigned int)CanCastTo;
    }
  }
  else if ( a2[1] == *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data2
         && a2[2] == *(_DWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4
         && a2[3] == *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data4[4] )
  {
    *a3 = a1;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
    return 0;
  }
  CanCastTo = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IHandlerAccessChange>::CanCastTo(a1 + 8);
  if ( CanCastTo >= 0 )
    goto LABEL_12;
  return (unsigned int)CanCastTo;
}

```

## disassembly

```asm
0x180002990  push    rbx
0x180002992  sub     rsp, 20h
0x180002996  mov     qword ptr [r8], 0
0x18000299d  cmp     dword ptr [rdx], 0
0x1800029a0  jnz     short loc_1800029D6
0x1800029a2  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x1800029a8  cmp     [rdx+4], eax
0x1800029ab  jnz     short loc_180002A06
0x1800029ad  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x1800029b3  cmp     [rdx+8], eax
0x1800029b6  jnz     short loc_180002A06
0x1800029b8  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x1800029be  cmp     [rdx+0Ch], eax
0x1800029c1  jnz     short loc_180002A06
0x1800029c3  mov     [r8], rcx
0x1800029c6  mov     rax, [rcx]
0x1800029c9  mov     rax, [rax+8]
0x1800029cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029d2  xor     eax, eax
0x1800029d4  jmp     short loc_180002A26
0x1800029d6  cmp     dword ptr [rdx], 8D540BDDh
0x1800029dc  jnz     short loc_180002A06
0x1800029de  mov     eax, dword ptr cs:_GUID_8d540bdd_316f_4204_ac18_799fffd29f12.Data2
0x1800029e4  cmp     [rdx+4], eax
0x1800029e7  jnz     short loc_180002A06
0x1800029e9  mov     eax, dword ptr cs:_GUID_8d540bdd_316f_4204_ac18_799fffd29f12.Data4
0x1800029ef  cmp     [rdx+8], eax
0x1800029f2  jnz     short loc_180002A06
0x1800029f4  mov     eax, dword ptr cs:_GUID_8d540bdd_316f_4204_ac18_799fffd29f12.Data4+4
0x1800029fa  cmp     [rdx+0Ch], eax
0x1800029fd  jnz     short loc_180002A06
0x1800029ff  mov     [r8], rcx
0x180002a02  xor     ebx, ebx
0x180002a04  jmp     short loc_180002A15
0x180002a06  add     rcx, 8
0x180002a0a  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIHandlerAccessChange@@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IHandlerAccessChange>::CanCastTo(_GUID const &,void * *,bool *)
0x180002a0f  mov     ebx, eax
0x180002a11  test    eax, eax
0x180002a13  js      short loc_180002A24
0x180002a15  mov     rcx, [r8]
0x180002a18  mov     rdx, [rcx]
0x180002a1b  mov     rax, [rdx+8]
0x180002a1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a24  mov     eax, ebx
0x180002a26  add     rsp, 20h
0x180002a2a  pop     rbx
0x180002a2b  retn
```
