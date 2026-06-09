# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)

- ea: `0x180006870`
- end: `0x18000694e`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006960`

## callees

- `0x180006870`
- `0x18000b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>,Microsoft::WRL::FtmBase>::QueryInterface(
        __int64 a1,
        _DWORD *a2,
        __int64 *a3)
{
  unsigned int v3; // ebx
  __int64 v4; // rcx
  int v5; // eax

  v3 = 0;
  *a3 = 0;
  if ( *a2 )
  {
    if ( *a2 == -754544154
      && a2[1] == *(_DWORD *)&GUID_d30691e6_60a0_59c9_8965_5bbe282e8208.Data2
      && a2[2] == *(_DWORD *)GUID_d30691e6_60a0_59c9_8965_5bbe282e8208.Data4
      && a2[3] == *(_DWORD *)&GUID_d30691e6_60a0_59c9_8965_5bbe282e8208.Data4[4] )
    {
      *a3 = a1;
LABEL_22:
      a1 = *a3;
      goto LABEL_6;
    }
LABEL_12:
    v4 = a1 + 8;
    if ( *a2 == -1796592748 )
    {
      if ( a2[1] != *(_DWORD *)&GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
        || a2[2] != *(_DWORD *)GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4 )
      {
        return (unsigned int)-2147467262;
      }
      v5 = *(_DWORD *)&GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4[4];
    }
    else
    {
      if ( *a2 != 3
        || a2[1] != *(_DWORD *)&GUID_00000003_0000_0000_c000_000000000046.Data2
        || a2[2] != *(_DWORD *)GUID_00000003_0000_0000_c000_000000000046.Data4 )
      {
        return (unsigned int)-2147467262;
      }
      v5 = *(_DWORD *)&GUID_00000003_0000_0000_c000_000000000046.Data4[4];
    }
    if ( a2[3] == v5 )
    {
      *a3 = v4;
      goto LABEL_22;
    }
    return (unsigned int)-2147467262;
  }
  if ( a2[1] != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data2
    || a2[2] != *(_DWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4
    || a2[3] != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data4[4] )
  {
    goto LABEL_12;
  }
  *a3 = a1;
LABEL_6:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  return v3;
}

```

## disassembly

```asm
0x180006870  push    rbx
0x180006872  sub     rsp, 20h
0x180006876  xor     ebx, ebx
0x180006878  mov     [r8], rbx
0x18000687b  cmp     [rdx], ebx
0x18000687d  jnz     short loc_1800068B4
0x18000687f  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x180006885  cmp     [rdx+4], eax
0x180006888  jnz     short loc_1800068E2
0x18000688a  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x180006890  cmp     [rdx+8], eax
0x180006893  jnz     short loc_1800068E2
0x180006895  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x18000689b  cmp     [rdx+0Ch], eax
0x18000689e  jnz     short loc_1800068E2
0x1800068a0  mov     [r8], rcx
0x1800068a3  mov     rax, [rcx]
0x1800068a6  mov     rax, [rax+8]
0x1800068aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068af  jmp     loc_180006945
0x1800068b4  cmp     dword ptr [rdx], 0D30691E6h
0x1800068ba  jnz     short loc_1800068E2
0x1800068bc  mov     eax, dword ptr cs:_GUID_d30691e6_60a0_59c9_8965_5bbe282e8208.Data2
0x1800068c2  cmp     [rdx+4], eax
0x1800068c5  jnz     short loc_1800068E2
0x1800068c7  mov     eax, dword ptr cs:_GUID_d30691e6_60a0_59c9_8965_5bbe282e8208.Data4
0x1800068cd  cmp     [rdx+8], eax
0x1800068d0  jnz     short loc_1800068E2
0x1800068d2  mov     eax, dword ptr cs:_GUID_d30691e6_60a0_59c9_8965_5bbe282e8208.Data4+4
0x1800068d8  cmp     [rdx+0Ch], eax
0x1800068db  jnz     short loc_1800068E2
0x1800068dd  mov     [r8], rcx
0x1800068e0  jmp     short loc_180006938
0x1800068e2  add     rcx, 8
0x1800068e6  cmp     dword ptr [rdx], 94EA2B94h
0x1800068ec  jnz     short loc_18000690C
0x1800068ee  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
0x1800068f4  cmp     [rdx+4], eax
0x1800068f7  jnz     short loc_180006940
0x1800068f9  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4
0x1800068ff  cmp     [rdx+8], eax
0x180006902  jnz     short loc_180006940
0x180006904  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4+4
0x18000690a  jmp     short loc_18000692D
0x18000690c  cmp     dword ptr [rdx], 3
0x18000690f  jnz     short loc_180006940
0x180006911  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data2
0x180006917  cmp     [rdx+4], eax
0x18000691a  jnz     short loc_180006940
0x18000691c  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4
0x180006922  cmp     [rdx+8], eax
0x180006925  jnz     short loc_180006940
0x180006927  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4+4
0x18000692d  cmp     [rdx+0Ch], eax
0x180006930  jnz     short loc_180006940
0x180006932  mov     rax, r8
0x180006935  mov     [rax], rcx
0x180006938  mov     rcx, [r8]
0x18000693b  jmp     loc_1800068A3
0x180006940  mov     ebx, 80004002h
0x180006945  mov     eax, ebx
0x180006947  add     rsp, 20h
0x18000694b  pop     rbx
0x18000694c  retn
```
