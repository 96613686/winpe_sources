# CXMLReader::CXMLReader(void)

- ea: `0x180022fa8`
- end: `0x180023160`
- name: `??0CXMLReader@@QEAA@XZ`
- size: `440`
- prototype: `CXMLReader *__fastcall(CXMLReader *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013ea4`

## callees

- `0x18000a1c0`
- `0x18001a54c`

## pseudocode

```c
CXMLReader *__fastcall CXMLReader::CXMLReader(CXMLReader *this)
{
  wchar_t *v2; // rcx
  CXMLReader *result; // rax

  ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::CComObjectRootEx<ATL::CComMultiThreadModel>((_DWORD *)this + 2);
  v2 = `CXMLReader::CNotUpdt_BidGeneric::BidObtainID'::`7'::_bidPtrSA_051_477;
  *(_QWORD *)this = &CXMLReader::`vftable';
  *((_DWORD *)this + 6) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_DWORD *)this + 10) = 0;
  *((_DWORD *)this + 12) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_DWORD *)this + 20) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_DWORD *)this + 24) = 0;
  *((_DWORD *)this + 26) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_DWORD *)this + 40) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_DWORD *)this + 44) = 0;
  *((_DWORD *)this + 46) = 0;
  *((_QWORD *)this + 24) = 0;
  *((_QWORD *)this + 25) = 0;
  *((_DWORD *)this + 52) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_DWORD *)this + 56) = 0;
  *((_DWORD *)this + 58) = 0;
  *((_QWORD *)this + 30) = 0;
  *((_QWORD *)this + 31) = 0;
  *((_DWORD *)this + 64) = 0;
  *((_QWORD *)this + 33) = 0;
  *((_DWORD *)this + 68) = 0;
  *((_DWORD *)this + 70) = 0;
  *((_QWORD *)this + 36) = 0;
  *((_QWORD *)this + 37) = 0;
  *((_DWORD *)this + 76) = 0;
  *((_QWORD *)this + 39) = 0;
  *((_DWORD *)this + 80) = 0;
  *((_DWORD *)this + 82) = 0;
  *((_QWORD *)this + 42) = 0;
  *((_QWORD *)this + 43) = 0;
  *((_DWORD *)this + 88) = 0;
  *((_QWORD *)this + 45) = 0;
  *((_DWORD *)this + 92) = 0;
  *((_DWORD *)this + 94) = 0;
  *((_QWORD *)this + 48) = 0;
  *((_QWORD *)this + 49) = 0;
  *((_DWORD *)this + 104) = 0;
  *((_QWORD *)this + 53) = 0;
  *((_DWORD *)this + 108) = 0;
  *((_DWORD *)this + 110) = 0;
  *((_DWORD *)this + 126) = 0;
  *((_QWORD *)this + 62) = &CXMLReader::CNotUpdt_BidGeneric::`vftable';
  *((_DWORD *)this + 126) = bidObtainItemIDW(v2, (char *)this + 496);
  result = this;
  *(_QWORD *)((char *)this + 476) = 8;
  *((_QWORD *)this + 17) = (char *)this + 24;
  *((_QWORD *)this + 56) = 0;
  *((_BYTE *)this + 400) = 0;
  *((_BYTE *)this + 472) = 0;
  *((_QWORD *)this + 61) = 0;
  *((_QWORD *)this + 57) = 0;
  *((_QWORD *)this + 58) = 0;
  *((_QWORD *)this + 51) = 0;
  return result;
}

```

## disassembly

```asm
0x180022fa8  push    rbx
0x180022faa  push    rbp
0x180022fab  push    rsi
0x180022fac  push    rdi
0x180022fad  sub     rsp, 28h
0x180022fb1  mov     rsi, rcx
0x180022fb4  add     rcx, 8
0x180022fb8  call    ??0?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::CComObjectRootEx<ATL::CComMultiThreadModel>(void)
0x180022fbd  xor     ebp, ebp
0x180022fbf  mov     rcx, cs:?_bidPtrSA_051_477@?6??BidObtainID@CNotUpdt_BidGeneric@CXMLReader@@AEAAHPEBX@Z@4REBGEB; ushort const * const `CXMLReader::CNotUpdt_BidGeneric::BidObtainID(void const *)'::`7'::_bidPtrSA_051_477
0x180022fc6  lea     rdi, [rsi+18h]
0x180022fca  lea     rbx, [rsi+1F0h]
0x180022fd1  lea     rax, ??_7CXMLReader@@6B@; const CXMLReader::`vftable'
0x180022fd8  mov     rdx, rbx
0x180022fdb  mov     [rsi], rax
0x180022fde  lea     rax, ??_7CNotUpdt_BidGeneric@CXMLReader@@6B@; const CXMLReader::CNotUpdt_BidGeneric::`vftable'
0x180022fe5  mov     [rdi], ebp
0x180022fe7  mov     [rdi+8], rbp
0x180022feb  mov     [rdi+10h], ebp
0x180022fee  mov     [rdi+18h], ebp
0x180022ff1  mov     [rdi+20h], rbp
0x180022ff5  mov     [rdi+28h], rbp
0x180022ff9  mov     [rdi+30h], rbp
0x180022ffd  mov     [rsi+50h], ebp
0x180023000  mov     [rsi+58h], rbp
0x180023004  mov     [rsi+60h], ebp
0x180023007  mov     [rsi+68h], ebp
0x18002300a  mov     [rsi+70h], rbp
0x18002300e  mov     [rsi+78h], rbp
0x180023012  mov     [rsi+80h], rbp
0x180023019  mov     [rsi+90h], rbp
0x180023020  mov     [rsi+98h], rbp
0x180023027  mov     [rsi+0A0h], ebp
0x18002302d  mov     [rsi+0A8h], rbp
0x180023034  mov     [rsi+0B0h], ebp
0x18002303a  mov     [rsi+0B8h], ebp
0x180023040  mov     [rsi+0C0h], rbp
0x180023047  mov     [rsi+0C8h], rbp
0x18002304e  mov     [rsi+0D0h], ebp
0x180023054  mov     [rsi+0D8h], rbp
0x18002305b  mov     [rsi+0E0h], ebp
0x180023061  mov     [rsi+0E8h], ebp
0x180023067  mov     [rsi+0F0h], rbp
0x18002306e  mov     [rsi+0F8h], rbp
0x180023075  mov     [rsi+100h], ebp
0x18002307b  mov     [rsi+108h], rbp
0x180023082  mov     [rsi+110h], ebp
0x180023088  mov     [rsi+118h], ebp
0x18002308e  mov     [rsi+120h], rbp
0x180023095  mov     [rsi+128h], rbp
0x18002309c  mov     [rsi+130h], ebp
0x1800230a2  mov     [rsi+138h], rbp
0x1800230a9  mov     [rsi+140h], ebp
0x1800230af  mov     [rsi+148h], ebp
0x1800230b5  mov     [rsi+150h], rbp
0x1800230bc  mov     [rsi+158h], rbp
0x1800230c3  mov     [rsi+160h], ebp
0x1800230c9  mov     [rsi+168h], rbp
0x1800230d0  mov     [rsi+170h], ebp
0x1800230d6  mov     [rsi+178h], ebp
0x1800230dc  mov     [rsi+180h], rbp
0x1800230e3  mov     [rsi+188h], rbp
0x1800230ea  mov     [rsi+1A0h], ebp
0x1800230f0  mov     [rsi+1A8h], rbp
0x1800230f7  mov     [rsi+1B0h], ebp
0x1800230fd  mov     [rsi+1B8h], ebp
0x180023103  mov     [rbx+8], ebp
0x180023106  mov     [rbx], rax
0x180023109  call    _bidObtainItemIDW
0x18002310e  mov     [rbx+8], eax
0x180023111  mov     rax, rsi
0x180023114  mov     qword ptr [rsi+1DCh], 8
0x18002311f  mov     [rsi+88h], rdi
0x180023126  mov     [rsi+1C0h], rbp
0x18002312d  mov     [rsi+190h], bpl
0x180023134  mov     [rsi+1D8h], bpl
0x18002313b  mov     [rsi+1E8h], rbp
0x180023142  mov     [rsi+1C8h], rbp
0x180023149  mov     [rsi+1D0h], rbp
0x180023150  mov     [rsi+198h], rbp
0x180023157  add     rsp, 28h
0x18002315b  pop     rdi
0x18002315c  pop     rsi
0x18002315d  pop     rbp
0x18002315e  pop     rbx
0x18002315f  retn
```
