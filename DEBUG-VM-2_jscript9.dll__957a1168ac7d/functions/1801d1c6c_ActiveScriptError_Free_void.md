# ActiveScriptError::Free(void)

- ea: `0x1801d1c6c`
- end: `0x1801d1de9`
- name: `?Free@ActiveScriptError@@AEAAXXZ`
- size: `381`
- prototype: `void __fastcall(ActiveScriptError *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1801d0d58`

## callees

- `0x180068e3c`
- `0x18010e564`
- `0x1801d1c6c`
- `0x18035e010`

## import_xrefs

- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801d1c8e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801d1ccc`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801d1ce4`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801d1c8e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801d1ccc`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801d1ce4`
- `OLEAUT32!__imp_SysFreeString` at `0x1801d1d0d`
- `OLEAUT32!__imp_SysFreeString` at `0x1801d1d3e`
- `OLEAUT32!__imp_SysFreeString` at `0x1801d1d5b`
- `OLEAUT32!__imp_SysFreeString` at `0x1801d1d78`
- `OLEAUT32!__imp_SysFreeString` at `0x1801d1d0d`
- `OLEAUT32!__imp_SysFreeString` at `0x1801d1d3e`
- `OLEAUT32!__imp_SysFreeString` at `0x1801d1d5b`
- `OLEAUT32!__imp_SysFreeString` at `0x1801d1d78`

## pseudocode

```c
void __fastcall ActiveScriptError::Free(ActiveScriptError *this)
{
  unsigned int v2; // esi
  LPVOID *i; // rdi
  __int64 v4; // rbp
  __int64 v5; // rcx
  OLECHAR *v6; // rcx
  OLECHAR *v7; // rcx
  OLECHAR *v8; // rcx
  OLECHAR *v9; // rcx
  __int64 v10; // rcx
  char *v11; // rdx

  FreeExcepInfo((struct tagEXCEPINFO *)((char *)this + 56));
  CoTaskMemFree(*((LPVOID *)this + 17));
  v2 = 0;
  for ( i = (LPVOID *)((char *)this + 152); v2 < *((_DWORD *)this + 36); ++v2 )
  {
    v4 = 32LL * v2;
    v5 = *(_QWORD *)((char *)*i + v4 + 24);
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    CoTaskMemFree(*(LPVOID *)((char *)*i + v4 + 8));
  }
  if ( *i )
    CoTaskMemFree(*i);
  *i = 0;
  *((_DWORD *)this + 36) = 0;
  v6 = (OLECHAR *)*((_QWORD *)this + 30);
  *((_QWORD *)this + 17) = 0;
  SysFreeString(v6);
  v7 = (OLECHAR *)*((_QWORD *)this + 21);
  *((_QWORD *)this + 27) = 0;
  *((_DWORD *)this + 56) = 0;
  *((_DWORD *)this + 57) = -1;
  if ( v7 )
  {
    SysFreeString(v7);
    *((_QWORD *)this + 21) = 0;
  }
  v8 = (OLECHAR *)*((_QWORD *)this + 20);
  if ( v8 )
  {
    SysFreeString(v8);
    *((_QWORD *)this + 20) = 0;
  }
  v9 = (OLECHAR *)*((_QWORD *)this + 22);
  if ( v9 )
  {
    SysFreeString(v9);
    *((_QWORD *)this + 22) = 0;
  }
  v10 = *((_QWORD *)this + 23);
  if ( v10 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    *((_QWORD *)this + 23) = 0;
  }
  v11 = (char *)*((_QWORD *)this + 25);
  if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFELL )
  {
    Recycler::RootRelease(*((Recycler **)this + 26), v11, 0);
    *((_QWORD *)this + 25) = 0;
  }
}

```

## disassembly

```asm
0x1801d1c6c  mov     [rsp+arg_0], rcx
0x1801d1c71  push    rbx
0x1801d1c72  push    rbp
0x1801d1c73  push    rsi
0x1801d1c74  push    rdi
0x1801d1c75  sub     rsp, 28h
0x1801d1c79  mov     rbx, [rsp+48h+arg_0]
0x1801d1c7e  lea     rcx, [rbx+38h]; struct tagEXCEPINFO *
0x1801d1c82  call    ?FreeExcepInfo@@YAXPEAUtagEXCEPINFO@@@Z; FreeExcepInfo(tagEXCEPINFO *)
0x1801d1c87  mov     rcx, [rbx+88h]; pv
0x1801d1c8e  call    cs:__imp_CoTaskMemFree
0x1801d1c94  xor     esi, esi
0x1801d1c96  lea     rdi, [rbx+98h]
0x1801d1c9d  cmp     [rbx+90h], esi
0x1801d1ca3  jbe     short loc_1801D1CDC
0x1801d1ca5  mov     rax, [rdi]
0x1801d1ca8  mov     ebp, esi
0x1801d1caa  shl     rbp, 5
0x1801d1cae  mov     rcx, [rax+rbp+18h]
0x1801d1cb3  test    rcx, rcx
0x1801d1cb6  jz      short loc_1801D1CC4
0x1801d1cb8  mov     rax, [rcx]
0x1801d1cbb  mov     rax, [rax+10h]
0x1801d1cbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d1cc4  mov     rcx, [rdi]
0x1801d1cc7  mov     rcx, [rcx+rbp+8]; pv
0x1801d1ccc  call    cs:__imp_CoTaskMemFree
0x1801d1cd2  inc     esi
0x1801d1cd4  cmp     esi, [rbx+90h]
0x1801d1cda  jb      short loc_1801D1CA5
0x1801d1cdc  mov     rcx, [rdi]; pv
0x1801d1cdf  test    rcx, rcx
0x1801d1ce2  jz      short loc_1801D1CEA
0x1801d1ce4  call    cs:__imp_CoTaskMemFree
0x1801d1cea  mov     qword ptr [rdi], 0
0x1801d1cf1  mov     dword ptr [rbx+90h], 0
0x1801d1cfb  mov     rcx, [rbx+0F0h]; bstrString
0x1801d1d02  mov     qword ptr [rbx+88h], 0
0x1801d1d0d  call    cs:__imp_SysFreeString
0x1801d1d13  mov     rcx, [rbx+0A8h]; bstrString
0x1801d1d1a  mov     qword ptr [rbx+0D8h], 0
0x1801d1d25  mov     dword ptr [rbx+0E0h], 0
0x1801d1d2f  mov     dword ptr [rbx+0E4h], 0FFFFFFFFh
0x1801d1d39  test    rcx, rcx
0x1801d1d3c  jz      short loc_1801D1D4F
0x1801d1d3e  call    cs:__imp_SysFreeString
0x1801d1d44  mov     qword ptr [rbx+0A8h], 0
0x1801d1d4f  mov     rcx, [rbx+0A0h]; bstrString
0x1801d1d56  test    rcx, rcx
0x1801d1d59  jz      short loc_1801D1D6C
0x1801d1d5b  call    cs:__imp_SysFreeString
0x1801d1d61  mov     qword ptr [rbx+0A0h], 0
0x1801d1d6c  mov     rcx, [rbx+0B0h]; bstrString
0x1801d1d73  test    rcx, rcx
0x1801d1d76  jz      short loc_1801D1D89
0x1801d1d78  call    cs:__imp_SysFreeString
0x1801d1d7e  mov     qword ptr [rbx+0B0h], 0
0x1801d1d89  mov     rcx, [rbx+0B8h]
0x1801d1d90  test    rcx, rcx
0x1801d1d93  jz      short loc_1801D1DAC
0x1801d1d95  mov     rax, [rcx]
0x1801d1d98  mov     rax, [rax+10h]
0x1801d1d9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d1da1  mov     qword ptr [rbx+0B8h], 0
0x1801d1dac  mov     rdx, [rbx+0C8h]; void *
0x1801d1db3  mov     rcx, 0FFFFFFFFFFFEh
0x1801d1dbd  lea     rax, [rdx-1]
0x1801d1dc1  cmp     rax, rcx
0x1801d1dc4  ja      short loc_1801D1DE0
0x1801d1dc6  mov     rcx, [rbx+0D0h]; this
0x1801d1dcd  xor     r8d, r8d; unsigned int *
0x1801d1dd0  call    ?RootRelease@Recycler@@QEAAXPEAXPEAI@Z; Recycler::RootRelease(void *,uint *)
0x1801d1dd5  mov     qword ptr [rbx+0C8h], 0
0x1801d1de0  add     rsp, 28h
0x1801d1de4  pop     rdi
0x1801d1de5  pop     rsi
0x1801d1de6  pop     rbp
0x1801d1de7  pop     rbx
0x1801d1de8  retn
```
