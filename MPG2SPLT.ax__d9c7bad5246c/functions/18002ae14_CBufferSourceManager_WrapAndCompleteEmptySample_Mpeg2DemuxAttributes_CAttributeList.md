# CBufferSourceManager::WrapAndCompleteEmptySample(Mpeg2DemuxAttributes::CAttributeList *)

- ea: `0x18002ae14`
- end: `0x18002aee8`
- name: `?WrapAndCompleteEmptySample@CBufferSourceManager@@IEAAJPEAVCAttributeList@Mpeg2DemuxAttributes@@@Z`
- size: `212`
- prototype: `__int64 __fastcall(CBufferSourceManager *__hidden this, struct Mpeg2DemuxAttributes::CAttributeList *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002d4e0`
- `0x18002d710`

## callees

- `0x18002ae14`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall CBufferSourceManager::WrapAndCompleteEmptySample(
        CBufferSourceManager *this,
        struct Mpeg2DemuxAttributes::CAttributeList *a2)
{
  __int64 v4; // rcx
  int v5; // edi
  _DWORD v7[4]; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v8; // [rsp+78h] [rbp+28h] BYREF
  __int64 v9; // [rsp+80h] [rbp+30h] BYREF
  __int64 v10; // [rsp+88h] [rbp+38h] BYREF

  if ( !a2 || *((int *)a2 + 40) <= 0 )
    return 2147549183LL;
  v4 = *((_QWORD *)this + 1);
  v9 = 0;
  v7[0] = 1;
  v7[1] = 1;
  v10 = 0;
  v8 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64 *, unsigned int *))(*(_QWORD *)v4 + 24LL))(
         v4,
         &v10,
         &v9,
         &v8);
  if ( v5 >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD, _DWORD, _DWORD *, struct Mpeg2DemuxAttributes::CAttributeList *))(**((_QWORD **)this + 1) + 40LL))(
           *((_QWORD *)this + 1),
           v10,
           v9,
           0,
           0,
           v7,
           a2);
    (*(void (__fastcall **)(_QWORD, __int64, __int64, _QWORD))(**((_QWORD **)this + 1) + 48LL))(
      *((_QWORD *)this + 1),
      v10,
      v9,
      v8);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002ae14  mov     [rsp-18h+arg_0], rbx
0x18002ae19  push    rbp
0x18002ae1a  push    rsi
0x18002ae1b  push    rdi
0x18002ae1c  mov     rbp, rsp
0x18002ae1f  sub     rsp, 50h
0x18002ae23  mov     rbx, rdx
0x18002ae26  mov     rsi, rcx
0x18002ae29  test    rdx, rdx
0x18002ae2c  jz      loc_18002AED6
0x18002ae32  cmp     dword ptr [rdx+0A0h], 0
0x18002ae39  jle     loc_18002AED6
0x18002ae3f  mov     rcx, [rcx+8]
0x18002ae43  lea     r9, [rbp+arg_8]
0x18002ae47  mov     eax, 1
0x18002ae4c  mov     [rbp+arg_10], 0
0x18002ae54  mov     [rbp+var_10], eax
0x18002ae57  lea     r8, [rbp+arg_10]
0x18002ae5b  mov     [rbp+var_C], eax
0x18002ae5e  lea     rdx, [rbp+arg_18]
0x18002ae62  mov     [rbp+arg_18], 0
0x18002ae6a  mov     [rbp+arg_8], 0
0x18002ae71  mov     rax, [rcx]
0x18002ae74  mov     rax, [rax+18h]
0x18002ae78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae7d  mov     edi, eax
0x18002ae7f  test    eax, eax
0x18002ae81  js      short loc_18002AED2
0x18002ae83  mov     rcx, [rsi+8]
0x18002ae87  lea     rdx, [rbp+var_10]
0x18002ae8b  mov     r8, [rbp+arg_10]
0x18002ae8f  xor     r9d, r9d
0x18002ae92  mov     [rsp+50h+var_20], rbx
0x18002ae97  mov     [rsp+50h+var_28], rdx
0x18002ae9c  mov     rax, [rcx]
0x18002ae9f  mov     rdx, [rbp+arg_18]
0x18002aea3  mov     [rsp+50h+var_30], 0
0x18002aeab  mov     rax, [rax+28h]
0x18002aeaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aeb4  mov     rcx, [rsi+8]
0x18002aeb8  mov     edi, eax
0x18002aeba  mov     r9d, [rbp+arg_8]
0x18002aebe  mov     r8, [rbp+arg_10]
0x18002aec2  mov     rdx, [rbp+arg_18]
0x18002aec6  mov     rax, [rcx]
0x18002aec9  mov     rax, [rax+30h]
0x18002aecd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aed2  mov     eax, edi
0x18002aed4  jmp     short loc_18002AEDB
0x18002aed6  mov     eax, 8000FFFFh
0x18002aedb  mov     rbx, [rsp+50h+arg_0]
0x18002aee0  add     rsp, 50h
0x18002aee4  pop     rdi
0x18002aee5  pop     rsi
0x18002aee6  pop     rbp
0x18002aee7  retn
```
