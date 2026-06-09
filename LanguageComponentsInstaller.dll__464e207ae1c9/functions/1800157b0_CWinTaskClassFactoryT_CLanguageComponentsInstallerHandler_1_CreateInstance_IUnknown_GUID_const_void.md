# CWinTaskClassFactoryT<CLanguageComponentsInstallerHandler,1>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1800157b0`
- end: `0x1800158b2`
- name: `?CreateInstance@?$CWinTaskClassFactoryT@VCLanguageComponentsInstallerHandler@@$00@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `258`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180003588`
- `0x180004118`
- `0x1800157b0`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CLanguageComponentsInstallerHandler,1>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  unsigned int v6; // edi
  _QWORD *v7; // rax
  _QWORD *v8; // rbx
  __int64 (__fastcall **v9)(_QWORD *, __int64, _QWORD *); // rax

  if ( a4 )
  {
    *a4 = 0;
    if ( a2 )
    {
      return (unsigned int)-2147221232;
    }
    else
    {
      v7 = operator new(0x128u, (const struct std::nothrow_t *)std::nothrow);
      v8 = v7;
      if ( v7 )
      {
        v7[1] = 0;
        *((_DWORD *)v7 + 4) = 0;
        v7[3] = -1;
        *((_DWORD *)v7 + 8) = 1;
        *((_DWORD *)v7 + 9) = 0;
        v7[5] = 0;
        v7[6] = 0;
        _InterlockedIncrement(&CWinTaskHandler::s_cInstances);
        v7[7] = 0;
        *v7 = &CLanguageComponentsInstallerHandler::`vftable';
        *((_BYTE *)v7 + 64) = 0;
        memset_0(v7 + 10, 0, 0xC0u);
        v8[9] = L"LanguageFeaturesOnDemand";
        v8[34] = 0;
        v8[35] = 0;
        v8[36] = 0;
        v9 = (__int64 (__fastcall **)(_QWORD *, __int64, _QWORD *))*v8;
        *((_DWORD *)v8 + 4) = 1;
        v6 = (*v9)(v8, a3, a4);
        (*(void (__fastcall **)(_QWORD *))(*v8 + 16LL))(v8);
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v6;
}

```

## disassembly

```asm
0x1800157b0  push    rbx
0x1800157b2  push    rbp
0x1800157b3  push    rsi
0x1800157b4  push    rdi
0x1800157b5  sub     rsp, 28h
0x1800157b9  xor     ebp, ebp
0x1800157bb  mov     rdi, r9
0x1800157be  mov     rsi, r8
0x1800157c1  test    r9, r9
0x1800157c4  jnz     short loc_1800157D0
0x1800157c6  mov     edi, 80070057h
0x1800157cb  jmp     loc_1800158A7
0x1800157d0  mov     [r9], rbp
0x1800157d3  test    rdx, rdx
0x1800157d6  jz      short loc_1800157E2
0x1800157d8  mov     edi, 80040110h
0x1800157dd  jmp     loc_1800158A7
0x1800157e2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800157e9  mov     ecx, 128h; unsigned __int64
0x1800157ee  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800157f3  mov     [rsp+48h+arg_18], rax
0x1800157f8  mov     rbx, rax
0x1800157fb  test    rax, rax
0x1800157fe  jz      loc_1800158A2
0x180015804  mov     [rax+8], rbp
0x180015808  mov     [rax+10h], ebp
0x18001580b  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x180015813  mov     dword ptr [rax+20h], 1
0x18001581a  mov     [rax+24h], ebp
0x18001581d  mov     [rax+28h], rbp
0x180015821  mov     [rax+30h], rbp
0x180015825  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18001582c  lea     rax, ??_7CLanguageComponentsInstallerHandler@@6B@; const CLanguageComponentsInstallerHandler::`vftable'
0x180015833  mov     [rbx+38h], rbp
0x180015837  lea     rcx, [rbx+50h]; void *
0x18001583b  mov     [rbx], rax
0x18001583e  xor     edx, edx; Val
0x180015840  mov     [rbx+40h], bpl
0x180015844  mov     r8d, 0C0h; Size
0x18001584a  call    memset_0
0x18001584f  lea     rax, aLanguagefeatur; "LanguageFeaturesOnDemand"
0x180015856  mov     [rbx+48h], rax
0x18001585a  mov     [rbx+110h], rbp
0x180015861  mov     [rbx+118h], rbp
0x180015868  mov     [rbx+120h], rbp
0x18001586f  test    rbx, rbx
0x180015872  jz      short loc_1800158A2
0x180015874  mov     rax, [rbx]
0x180015877  mov     r8, rdi
0x18001587a  mov     rdx, rsi
0x18001587d  mov     dword ptr [rbx+10h], 1
0x180015884  mov     rcx, rbx
0x180015887  mov     rax, [rax]
0x18001588a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001588f  mov     rdx, [rbx]
0x180015892  mov     edi, eax
0x180015894  mov     rcx, rbx
0x180015897  mov     rax, [rdx+10h]
0x18001589b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158a0  jmp     short loc_1800158A7
0x1800158a2  mov     edi, 8007000Eh
0x1800158a7  mov     eax, edi
0x1800158a9  add     rsp, 28h
0x1800158ad  pop     rdi
0x1800158ae  pop     rsi
0x1800158af  pop     rbp
0x1800158b0  pop     rbx
0x1800158b1  retn
```
