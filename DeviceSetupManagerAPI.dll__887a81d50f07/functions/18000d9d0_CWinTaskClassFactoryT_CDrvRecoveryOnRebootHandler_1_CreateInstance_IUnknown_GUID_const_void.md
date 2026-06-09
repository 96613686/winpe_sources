# CWinTaskClassFactoryT<CDrvRecoveryOnRebootHandler,1>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18000d9d0`
- end: `0x18000daab`
- name: `?CreateInstance@?$CWinTaskClassFactoryT@VCDrvRecoveryOnRebootHandler@@$00@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `219`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x18000137c`
- `0x18000d9d0`
- `0x18000f010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CDrvRecoveryOnRebootHandler,1>::CreateInstance(
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
        *v7 = &CDrvRecoveryOnRebootHandler::`vftable';
        *((_DWORD *)v7 + 4) = 1;
        v6 = ((__int64 (__fastcall *)(_QWORD *, __int64, _QWORD *))CDrvRecoveryOnRebootHandler::`vftable')(v7, a3, a4);
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
0x18000d9d0  mov     [rsp+arg_0], rbx
0x18000d9d5  mov     [rsp+arg_8], rsi
0x18000d9da  push    rdi
0x18000d9db  sub     rsp, 20h
0x18000d9df  mov     rdi, r9
0x18000d9e2  mov     rsi, r8
0x18000d9e5  test    r9, r9
0x18000d9e8  jnz     short loc_18000D9F4
0x18000d9ea  mov     edi, 80070057h
0x18000d9ef  jmp     loc_18000DA99
0x18000d9f4  mov     qword ptr [r9], 0
0x18000d9fb  test    rdx, rdx
0x18000d9fe  jz      short loc_18000DA0A
0x18000da00  mov     edi, 80040110h
0x18000da05  jmp     loc_18000DA99
0x18000da0a  mov     ecx, 38h ; '8'; Size
0x18000da0f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000da14  mov     [rsp+28h+arg_18], rax
0x18000da19  mov     rbx, rax
0x18000da1c  test    rax, rax
0x18000da1f  jz      short loc_18000DA94
0x18000da21  mov     qword ptr [rax+8], 0
0x18000da29  mov     ecx, 1
0x18000da2e  mov     dword ptr [rax+10h], 0
0x18000da35  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x18000da3d  mov     [rax+20h], ecx
0x18000da40  mov     dword ptr [rax+24h], 0
0x18000da47  mov     qword ptr [rax+28h], 0
0x18000da4f  mov     qword ptr [rax+30h], 0
0x18000da57  lock add cs:?s_cInstances@CWinTaskHandler@@0JC, ecx; long volatile CWinTaskHandler::s_cInstances
0x18000da5e  lea     rax, ??_7CDrvRecoveryOnRebootHandler@@6B@; const CDrvRecoveryOnRebootHandler::`vftable'
0x18000da65  mov     [rbx], rax
0x18000da68  test    rbx, rbx
0x18000da6b  jz      short loc_18000DA94
0x18000da6d  mov     rax, [rax]
0x18000da70  mov     r8, rdi
0x18000da73  mov     [rbx+10h], ecx
0x18000da76  mov     rdx, rsi
0x18000da79  mov     rcx, rbx
0x18000da7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da81  mov     rdx, [rbx]
0x18000da84  mov     edi, eax
0x18000da86  mov     rcx, rbx
0x18000da89  mov     rax, [rdx+10h]
0x18000da8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da92  jmp     short loc_18000DA99
0x18000da94  mov     edi, 8007000Eh
0x18000da99  mov     rbx, [rsp+28h+arg_0]
0x18000da9e  mov     eax, edi
0x18000daa0  mov     rsi, [rsp+28h+arg_8]
0x18000daa5  add     rsp, 20h
0x18000daa9  pop     rdi
0x18000daaa  retn
```
