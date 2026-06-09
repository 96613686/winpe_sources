# ATL::CComClassFactorySingleton<HtmlDocForParsingSiteUnmarshaller>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180003ef0`
- end: `0x18000404b`
- name: `?CreateInstance@?$CComClassFactorySingleton@VHtmlDocForParsingSiteUnmarshaller@@@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `347`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001160`
- `0x180001184`
- `0x180003bc8`
- `0x180003be4`
- `0x180003ef0`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003f55`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003f55`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004011`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004011`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a55c`

## pseudocode

```c
__int64 __fastcall ATL::CComClassFactorySingleton<HtmlDocForParsingSiteUnmarshaller>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  __int64 result; // rax
  _QWORD *v8; // r14
  int v9; // esi
  void *v10; // rax
  __int64 (__fastcall ***v11)(void *, GUID *, _QWORD *); // rdi
  int v12; // eax

  result = 2147500035LL;
  if ( a4 )
  {
    *a4 = 0;
    if ( a2 )
    {
      return 2147746064LL;
    }
    else
    {
      if ( !*(_DWORD *)(a1 + 72) )
      {
        v8 = (_QWORD *)(a1 + 80);
        if ( !*(_QWORD *)(a1 + 80) )
        {
          EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
          if ( !*(_DWORD *)(a1 + 72) && !*v8 )
          {
            v9 = -2147024882;
            v10 = operator new(0x20u);
            if ( v10 )
              v11 = (__int64 (__fastcall ***)(void *, GUID *, _QWORD *))ATL::CComObjectCached<HtmlDocForParsingSiteUnmarshaller>::CComObjectCached<HtmlDocForParsingSiteUnmarshaller>((__int64)v10);
            else
              v11 = 0;
            if ( v11 )
              v9 = 0;
            *(_DWORD *)(a1 + 72) = v9;
            if ( v9 >= 0 )
            {
              v12 = (**v11)(v11, &IID_IUnknown, v8);
              *(_DWORD *)(a1 + 72) = v12;
              if ( v12 < 0 )
              {
                ATL::CComObjectCached<HtmlDocForParsingSiteUnmarshaller>::~CComObjectCached<HtmlDocForParsingSiteUnmarshaller>((__int64)v11);
                operator delete(v11);
              }
            }
          }
          LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
        }
      }
      result = *(unsigned int *)(a1 + 72);
      if ( !(_DWORD)result )
        return (***(__int64 (__fastcall ****)(_QWORD, __int64, _QWORD *))(a1 + 80))(*(_QWORD *)(a1 + 80), a3, a4);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180003ef0  mov     [rsp+arg_8], rbx
0x180003ef5  mov     [rsp+arg_10], rsi
0x180003efa  mov     [rsp+arg_0], rcx
0x180003eff  push    rdi
0x180003f00  push    r12
0x180003f02  push    r13
0x180003f04  push    r14
0x180003f06  push    r15
0x180003f08  sub     rsp, 30h
0x180003f0c  mov     r15, r9
0x180003f0f  mov     r13, r8
0x180003f12  mov     rbx, rcx
0x180003f15  mov     eax, 80004003h
0x180003f1a  test    r9, r9
0x180003f1d  jz      loc_180004033
0x180003f23  mov     qword ptr [r9], 0
0x180003f2a  test    rdx, rdx
0x180003f2d  jz      short loc_180003F39
0x180003f2f  mov     eax, 80040110h
0x180003f34  jmp     loc_180004033
0x180003f39  cmp     dword ptr [rcx+48h], 0
0x180003f3d  jnz     loc_180004017
0x180003f43  lea     r14, [rcx+50h]
0x180003f47  cmp     qword ptr [r14], 0
0x180003f4b  jnz     loc_180004017
0x180003f51  add     rcx, 10h; lpCriticalSection
0x180003f55  call    cs:__imp_EnterCriticalSection
0x180003f5b  cmp     dword ptr [rbx+48h], 0
0x180003f5f  jnz     loc_18000400D
0x180003f65  cmp     qword ptr [r14], 0
0x180003f69  jnz     loc_18000400D
0x180003f6f  mov     [rsp+58h+arg_18], 0
0x180003f78  mov     [rsp+58h+arg_18], 0
0x180003f81  mov     esi, 8007000Eh
0x180003f86  mov     [rsp+58h+var_38], esi
0x180003f8a  mov     [rsp+58h+var_30], 0
0x180003f93  mov     ecx, 20h ; ' '; Size
0x180003f98  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003f9d  test    rax, rax
0x180003fa0  jz      short loc_180003FAF
0x180003fa2  mov     rcx, rax
0x180003fa5  call    ??0?$CComObjectCached@VHtmlDocForParsingSiteUnmarshaller@@@ATL@@QEAA@PEAX@Z; ATL::CComObjectCached<HtmlDocForParsingSiteUnmarshaller>::CComObjectCached<HtmlDocForParsingSiteUnmarshaller>(void *)
0x180003faa  mov     rdi, rax
0x180003fad  jmp     short loc_180003FB1
0x180003faf  xor     edi, edi
0x180003fb1  mov     [rsp+58h+var_30], rdi
0x180003fb6  test    rdi, rdi
0x180003fb9  jz      short loc_180003FD1
0x180003fbb  mov     [rsp+58h+var_38], 0
0x180003fc3  mov     [rsp+58h+var_38], 0
0x180003fcb  xor     esi, esi
0x180003fcd  mov     [rsp+58h+var_38], esi
0x180003fd1  mov     [rsp+58h+arg_18], rdi
0x180003fd6  mov     [rbx+48h], esi
0x180003fd9  test    esi, esi
0x180003fdb  js      short loc_18000400D
0x180003fdd  mov     rax, [rdi]
0x180003fe0  mov     r8, r14
0x180003fe3  lea     rdx, IID_IUnknown
0x180003fea  mov     rcx, rdi
0x180003fed  mov     rax, [rax]
0x180003ff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ff5  mov     [rbx+48h], eax
0x180003ff8  test    eax, eax
0x180003ffa  jns     short loc_18000400D
0x180003ffc  mov     rcx, rdi
0x180003fff  call    ??1?$CComObjectCached@VHtmlDocForParsingSiteUnmarshaller@@@ATL@@QEAA@XZ; ATL::CComObjectCached<HtmlDocForParsingSiteUnmarshaller>::~CComObjectCached<HtmlDocForParsingSiteUnmarshaller>(void)
0x180004004  mov     rcx, rdi; Block
0x180004007  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000400c  nop
0x18000400d  lea     rcx, [rbx+10h]; lpCriticalSection
0x180004011  call    cs:__imp_LeaveCriticalSection
0x180004017  mov     eax, [rbx+48h]
0x18000401a  test    eax, eax
0x18000401c  jnz     short loc_180004033
0x18000401e  mov     rcx, [rbx+50h]
0x180004022  mov     rax, [rcx]
0x180004025  mov     r8, r15
0x180004028  mov     rdx, r13
0x18000402b  mov     rax, [rax]
0x18000402e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004033  mov     rbx, [rsp+58h+arg_8]
0x180004038  mov     rsi, [rsp+58h+arg_10]
0x18000403d  add     rsp, 30h
0x180004041  pop     r15
0x180004043  pop     r14
0x180004045  pop     r13
0x180004047  pop     r12
0x180004049  pop     rdi
0x18000404a  retn
0x18000a546  push    rbp
0x18000a548  sub     rsp, 20h
0x18000a54c  mov     rbp, rdx
0x18000a54f  mov     rcx, [rbp+60h]
0x18000a553  add     rcx, 10h
0x18000a557  add     rsp, 20h
0x18000a55b  pop     rbp
0x18000a55c  jmp     cs:__imp_LeaveCriticalSection
```
