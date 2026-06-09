# GameInputReading::Create(void *,ReadingDataLayout const *,KeyboardLookupTable const *,GameInputDevice *,ReadingPoolElementPtr &&,GameInputReading * *)

- ea: `0x1800050c0`
- end: `0x1800051f8`
- name: `?Create@GameInputReading@@SAJPEAXPEBVReadingDataLayout@@PEBVKeyboardLookupTable@@PEAVGameInputDevice@@$$QEAVReadingPoolElementPtr@@PEAPEAV1@@Z`
- size: `312`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _QWORD *, volatile signed __int32 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180004690`

## callees

- `0x180001304`
- `0x1800050c0`
- `0x1800065d8`
- `0x180007e80`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800050ea`
- `ntdll!RtlAllocateHeap` at `0x1800050ea`

## string_xrefs

- `0x1800051a2`: `onecore\xbox\gameinput\client\GameInputReading.cpp`

## pseudocode

```c
__int64 __fastcall GameInputReading::Create(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        volatile signed __int32 **a6)
{
  volatile signed __int32 *Heap; // rax
  int v11; // r8d
  int v12; // r9d
  volatile signed __int32 *v13; // rbx
  int v15; // [rsp+40h] [rbp-38h] BYREF
  _QWORD v16[6]; // [rsp+48h] [rbp-30h] BYREF

  Heap = (volatile signed __int32 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x48u);
  v13 = Heap;
  if ( Heap )
  {
    *((_DWORD *)Heap + 4) = 0;
    *(_QWORD *)Heap = &GameInputReading::`vftable'{for `InterfaceHierarchy<IGameInputReading,IGameInputReadingPrivate>'};
    *((_QWORD *)Heap + 1) = &GameInputReading::`vftable'{for `InterfaceHierarchy<IGameInputRawDeviceReport,IGameInputRawDeviceReportPrivate>'};
    *((_QWORD *)Heap + 3) = a1;
    *((_QWORD *)Heap + 4) = a2;
    *((_QWORD *)Heap + 5) = a3;
    *((_QWORD *)Heap + 6) = a4;
    *((_QWORD *)Heap + 7) = *a5;
    *((_QWORD *)Heap + 8) = a5[1];
    *a5 = 0;
    _InterlockedIncrement(Heap + 4);
    GameInputClient::IncrementGlobalObjectCount();
    ++dword_1800696A0;
    GameInputClientDebugRefCountCheck();
    *a6 = v13;
    return 0;
  }
  else
  {
    *a6 = 0;
    if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 1) != 0 && (qword_180069018 & 1) == qword_180069018 )
    {
      LODWORD(a6) = -2147024882;
      v16[0] = "onecore\\xbox\\gameinput\\client\\GameInputReading.cpp";
      v15 = 34;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (unsigned int)v16,
        (unsigned int)&unk_180059618,
        v11,
        v12,
        (__int64)v16,
        (__int64)&v15,
        (__int64)&a6);
    }
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x1800050c0  push    rbx
0x1800050c2  push    rbp
0x1800050c3  push    rsi
0x1800050c4  push    rdi
0x1800050c5  push    r14
0x1800050c7  sub     rsp, 50h
0x1800050cb  mov     r14, rcx
0x1800050ce  mov     rbp, rdx
0x1800050d1  mov     rcx, gs:60h
0x1800050da  xor     edx, edx; Flags
0x1800050dc  mov     rsi, r8
0x1800050df  mov     rdi, r9
0x1800050e2  mov     rcx, [rcx+30h]; HeapHandle
0x1800050e6  lea     r8d, [rdx+48h]; Size
0x1800050ea  call    cs:__imp_RtlAllocateHeap
0x1800050f1  nop     dword ptr [rax+rax+00h]
0x1800050f6  xor     edx, edx
0x1800050f8  mov     rbx, rax
0x1800050fb  test    rax, rax
0x1800050fe  jz      short loc_18000516A
0x180005100  mov     rcx, [rsp+78h+arg_20]
0x180005108  mov     [rax+10h], edx
0x18000510b  lea     rax, ??_7GameInputReading@@6B?$InterfaceHierarchy@UIGameInputReading@@UIGameInputReadingPrivate@@@@@; const GameInputReading::`vftable'{for `InterfaceHierarchy<IGameInputReading,IGameInputReadingPrivate>'}
0x180005112  mov     [rbx], rax
0x180005115  lea     rax, ??_7GameInputReading@@6B?$InterfaceHierarchy@UIGameInputRawDeviceReport@@UIGameInputRawDeviceReportPrivate@@@@@; const GameInputReading::`vftable'{for `InterfaceHierarchy<IGameInputRawDeviceReport,IGameInputRawDeviceReportPrivate>'}
0x18000511c  mov     [rbx+8], rax
0x180005120  mov     [rbx+18h], r14
0x180005124  mov     [rbx+20h], rbp
0x180005128  mov     [rbx+28h], rsi
0x18000512c  mov     [rbx+30h], rdi
0x180005130  mov     rax, [rcx]
0x180005133  mov     [rbx+38h], rax
0x180005137  mov     rax, [rcx+8]
0x18000513b  mov     [rbx+40h], rax
0x18000513f  mov     [rcx], rdx
0x180005142  nop
0x180005143  lock inc dword ptr [rbx+10h]
0x180005147  nop
0x180005148  call    ?IncrementGlobalObjectCount@GameInputClient@@SAXXZ; GameInputClient::IncrementGlobalObjectCount(void)
0x18000514d  inc     cs:dword_1800696A0
0x180005153  call    GameInputClientDebugRefCountCheck
0x180005158  mov     rax, [rsp+78h+arg_28]
0x180005160  mov     [rax], rbx
0x180005163  xor     eax, eax
0x180005165  jmp     loc_1800051EC
0x18000516a  mov     rax, [rsp+78h+arg_28]
0x180005172  mov     ebx, 8007000Eh
0x180005177  mov     [rax], rdx
0x18000517a  mov     eax, cs:dword_180069000
0x180005180  cmp     eax, 2
0x180005183  jbe     short loc_1800051EA
0x180005185  mov     rcx, cs:qword_180069018
0x18000518c  mov     rax, cs:qword_180069010
0x180005193  test    al, 1
0x180005195  jz      short loc_1800051EA
0x180005197  mov     rax, rcx
0x18000519a  and     eax, 1
0x18000519d  cmp     rax, rcx
0x1800051a0  jnz     short loc_1800051EA
0x1800051a2  lea     rcx, aOnecoreXboxGam_6; "onecore\\xbox\\gameinput\\client\\GameI"...
0x1800051a9  mov     dword ptr [rsp+78h+arg_28], ebx
0x1800051b0  mov     [rsp+78h+var_30], rcx
0x1800051b5  lea     rdx, unk_180059618
0x1800051bc  lea     rcx, [rsp+78h+arg_28]
0x1800051c4  mov     [rsp+78h+var_38], 22h ; '"'
0x1800051cc  mov     [rsp+78h+var_48], rcx
0x1800051d1  lea     rcx, [rsp+78h+var_38]
0x1800051d6  mov     [rsp+78h+var_50], rcx
0x1800051db  lea     rcx, [rsp+78h+var_30]
0x1800051e0  mov     [rsp+78h+var_58], rcx
0x1800051e5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800051ea  mov     eax, ebx
0x1800051ec  add     rsp, 50h
0x1800051f0  pop     r14
0x1800051f2  pop     rdi
0x1800051f3  pop     rsi
0x1800051f4  pop     rbp
0x1800051f5  pop     rbx
0x1800051f6  retn
```
