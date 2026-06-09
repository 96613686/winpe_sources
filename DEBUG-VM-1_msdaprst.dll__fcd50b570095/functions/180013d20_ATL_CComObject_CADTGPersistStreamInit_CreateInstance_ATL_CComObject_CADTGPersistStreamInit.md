# ATL::CComObject<CADTGPersistStreamInit>::CreateInstance(ATL::CComObject<CADTGPersistStreamInit> * *)

- ea: `0x180013d20`
- end: `0x180013de5`
- name: `?CreateInstance@?$CComObject@VCADTGPersistStreamInit@@@ATL@@SAJPEAPEAV12@@Z`
- size: `197`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800146d0`

## callees

- `0x180001d94`
- `0x18000a1c0`
- `0x180013d20`
- `0x18001a54c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComObject<CADTGPersistStreamInit>::CreateInstance(unsigned __int8 **a1, unsigned int a2)
{
  __int64 result; // rax
  unsigned __int8 *v4; // rax
  unsigned __int8 *v5; // rdi
  unsigned int v6; // [rsp+20h] [rbp-18h] BYREF

  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  v4 = MMMAlloc(0x40u, a2);
  try
  {
    v5 = v4;
    if ( v4 )
    {
      ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::CComObjectRootEx<ATL::CComMultiThreadModel>((_DWORD *)v4 + 2);
      *(_QWORD *)v5 = &CADTGPersistStreamInit::`vftable';
      *((_DWORD *)v5 + 8) = 0;
      *((_QWORD *)v5 + 3) = &CADTGPersistStreamInit::CNotUpdt_BidGeneric::`vftable';
      *((_DWORD *)v5 + 8) = bidObtainItemIDW(
                              `CADTGPersistStreamInit::CNotUpdt_BidGeneric::BidObtainID'::`7'::_bidPtrSA_051_525[0],
                              v5 + 24);
      *((_QWORD *)v5 + 7) = 0;
      *((_WORD *)v5 + 22) = 0;
      *((_DWORD *)v5 + 10) = 0;
      *(_QWORD *)v5 = &ATL::CComObject<CADTGPersistStreamInit>::`vftable';
      _InterlockedIncrement(&dword_1800454E8);
    }
    else
    {
      v5 = 0;
    }
    result = v5 == 0 ? 0x8007000E : 0;
    *a1 = v5;
  }
  catch ( long v6 )
  {
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x180013d20  mov     [rsp+arg_8], rbx
0x180013d25  mov     [rsp+arg_10], rsi
0x180013d2a  push    rdi
0x180013d2b  sub     rsp, 30h
0x180013d2f  mov     rsi, rcx
0x180013d32  test    rcx, rcx
0x180013d35  jnz     short loc_180013D41
0x180013d37  mov     eax, 80004003h
0x180013d3c  jmp     loc_180013DD5
0x180013d41  mov     qword ptr [rcx], 0
0x180013d48  mov     ecx, 40h ; '@'; unsigned int
0x180013d4d  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x180013d52  mov     rdi, rax
0x180013d55  mov     [rsp+38h+arg_0], rax
0x180013d5a  test    rax, rax
0x180013d5d  jz      short loc_180013DBB
0x180013d5f  lea     rcx, [rax+8]
0x180013d63  call    ??0?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::CComObjectRootEx<ATL::CComMultiThreadModel>(void)
0x180013d68  lea     rax, ??_7CADTGPersistStreamInit@@6B@; const CADTGPersistStreamInit::`vftable'
0x180013d6f  mov     [rdi], rax
0x180013d72  mov     dword ptr [rdi+20h], 0
0x180013d79  lea     rax, ??_7CNotUpdt_BidGeneric@CADTGPersistStreamInit@@6B@; const CADTGPersistStreamInit::CNotUpdt_BidGeneric::`vftable'
0x180013d80  mov     [rdi+18h], rax
0x180013d84  lea     rdx, [rdi+18h]
0x180013d88  mov     rcx, cs:?_bidPtrSA_051_525@?6??BidObtainID@CNotUpdt_BidGeneric@CADTGPersistStreamInit@@AEAAHPEBX@Z@4REBGEB; ushort const * const `CADTGPersistStreamInit::CNotUpdt_BidGeneric::BidObtainID(void const *)'::`7'::_bidPtrSA_051_525
0x180013d8f  call    _bidObtainItemIDW
0x180013d94  mov     [rdi+20h], eax
0x180013d97  mov     qword ptr [rdi+38h], 0
0x180013d9f  xor     eax, eax
0x180013da1  mov     [rdi+2Ch], ax
0x180013da5  mov     [rdi+28h], eax
0x180013da8  lea     rax, ??_7?$CComObject@VCADTGPersistStreamInit@@@ATL@@6B@; const ATL::CComObject<CADTGPersistStreamInit>::`vftable'
0x180013daf  mov     [rdi], rax
0x180013db2  lock inc cs:dword_1800454E8
0x180013db9  jmp     short loc_180013DBD
0x180013dbb  xor     edi, edi
0x180013dbd  mov     rax, rdi
0x180013dc0  neg     rax
0x180013dc3  sbb     eax, eax
0x180013dc5  not     eax
0x180013dc7  and     eax, 8007000Eh
0x180013dcc  mov     [rsi], rdi
0x180013dcf  jmp     short loc_180013DD5
0x180013dd1  mov     eax, [rsp+38h+var_18]
0x180013dd5  mov     rbx, [rsp+38h+arg_8]
0x180013dda  mov     rsi, [rsp+38h+arg_10]
0x180013ddf  add     rsp, 30h
0x180013de3  pop     rdi
0x180013de4  retn
```
