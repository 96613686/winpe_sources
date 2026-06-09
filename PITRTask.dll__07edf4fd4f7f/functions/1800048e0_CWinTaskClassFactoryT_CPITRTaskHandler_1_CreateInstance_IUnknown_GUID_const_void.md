# CWinTaskClassFactoryT<CPITRTaskHandler,1>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1800048e0`
- end: `0x1800049bb`
- name: `?CreateInstance@?$CWinTaskClassFactoryT@VCPITRTaskHandler@@$00@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `219`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x1800014b4`
- `0x1800048e0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CPITRTaskHandler,1>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  unsigned int v6; // edi
  _QWORD *v7; // rax
  _QWORD *v8; // rbx

  if ( a4 )
  {
    *a4 = 0;
    if ( a2 )
    {
      return (unsigned int)-2147221232;
    }
    else
    {
      v7 = operator new(0x38u);
      v8 = v7;
      if ( v7 )
      {
        v7[1] = 0;
        *((_DWORD *)v7 + 4) = 0;
        v7[3] = -1;
        v7[4] = 1;
        v7[5] = 0;
        v7[6] = 0;
        _InterlockedAdd(&CWinTaskHandler::s_cInstances, 1u);
        *v7 = &CPITRTaskHandler::`vftable';
        *((_DWORD *)v7 + 4) = 1;
        v6 = ((__int64 (__fastcall *)(_QWORD *, __int64, _QWORD *))CPITRTaskHandler::`vftable')(v7, a3, a4);
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
0x1800048e0  mov     [rsp+arg_0], rbx
0x1800048e5  mov     [rsp+arg_8], rsi
0x1800048ea  push    rdi
0x1800048eb  sub     rsp, 20h
0x1800048ef  mov     rdi, r9
0x1800048f2  mov     rsi, r8
0x1800048f5  test    r9, r9
0x1800048f8  jnz     short loc_180004904
0x1800048fa  mov     edi, 80070057h
0x1800048ff  jmp     loc_1800049A9
0x180004904  mov     qword ptr [r9], 0
0x18000490b  test    rdx, rdx
0x18000490e  jz      short loc_18000491A
0x180004910  mov     edi, 80040110h
0x180004915  jmp     loc_1800049A9
0x18000491a  mov     ecx, 38h ; '8'; Size
0x18000491f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004924  mov     [rsp+28h+arg_18], rax
0x180004929  mov     rbx, rax
0x18000492c  test    rax, rax
0x18000492f  jz      short loc_1800049A4
0x180004931  mov     qword ptr [rax+8], 0
0x180004939  mov     ecx, 1
0x18000493e  mov     dword ptr [rax+10h], 0
0x180004945  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x18000494d  mov     [rax+20h], ecx
0x180004950  mov     dword ptr [rax+24h], 0
0x180004957  mov     qword ptr [rax+28h], 0
0x18000495f  mov     qword ptr [rax+30h], 0
0x180004967  lock add cs:?s_cInstances@CWinTaskHandler@@0JC, ecx; long volatile CWinTaskHandler::s_cInstances
0x18000496e  lea     rax, ??_7CPITRTaskHandler@@6B@; const CPITRTaskHandler::`vftable'
0x180004975  mov     [rbx], rax
0x180004978  test    rbx, rbx
0x18000497b  jz      short loc_1800049A4
0x18000497d  mov     rax, [rax]
0x180004980  mov     r8, rdi
0x180004983  mov     [rbx+10h], ecx
0x180004986  mov     rdx, rsi
0x180004989  mov     rcx, rbx
0x18000498c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004991  mov     rdx, [rbx]
0x180004994  mov     edi, eax
0x180004996  mov     rcx, rbx
0x180004999  mov     rax, [rdx+10h]
0x18000499d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049a2  jmp     short loc_1800049A9
0x1800049a4  mov     edi, 8007000Eh
0x1800049a9  mov     rbx, [rsp+28h+arg_0]
0x1800049ae  mov     eax, edi
0x1800049b0  mov     rsi, [rsp+28h+arg_8]
0x1800049b5  add     rsp, 20h
0x1800049b9  pop     rdi
0x1800049ba  retn
```
