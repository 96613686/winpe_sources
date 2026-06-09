# QueueGenericWorkItem(std::function<void (void)>)

- ea: `0x180008e00`
- end: `0x180009080`
- name: `?QueueGenericWorkItem@@YAJV?$function@$$A6AXXZ@std@@@Z`
- size: `640`
- prototype: ``
- caller_count: `31`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800026a4`
- `0x1800027b8`
- `0x180007570`
- `0x180007720`
- `0x180008050`
- `0x1800082a0`
- `0x1800089d0`
- `0x180009670`
- `0x18000d6f4`
- `0x18001efc0`
- `0x180023070`
- `0x1800257d8`
- `0x1800261c0`
- `0x180027110`
- `0x180028770`
- `0x18002c334`
- `0x18002df20`
- `0x18002ec30`
- `0x18002fb70`
- `0x1800300e4`
- `0x180030c74`
- `0x180040940`
- `0x180040a60`
- `0x180040ce0`
- `0x180040fe0`
- `0x1800420ec`
- `0x18004214c`
- `0x180042390`
- `0x180043d80`
- `0x180044220`
- `0x1800445b0`

## callees

- `0x180008e00`
- `0x18000a384`
- `0x18001e600`
- `0x18002ce0c`
- `0x180031eb0`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008e9b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008e9b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008e8a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008e8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008fdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008fdc`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x180008fd2`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x180008fd2`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall QueueGenericWorkItem(__int64 *a1)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rbx
  __int64 (__fastcall ***v4)(_QWORD, _BYTE *); // rcx
  HANDLE ProcessHeap; // rax
  _DWORD *v6; // rax
  _DWORD *v7; // rdi
  volatile signed __int32 *v8; // rsi
  _BYTE *v9; // rdx
  const char *v10; // r9
  __int64 *v11; // rcx
  __int64 v12; // rdx
  __int64 result; // rax
  __int64 v14; // rdx
  signed int LastError; // eax
  unsigned int v16; // ebx
  __int64 *v17; // rcx
  int v18; // [rsp+20h] [rbp-78h]
  _BYTE v19[56]; // [rsp+28h] [rbp-70h] BYREF
  _BYTE *v20; // [rsp+60h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  _QWORD *v23; // [rsp+A8h] [rbp+10h] BYREF
  _BYTE *v24; // [rsp+B0h] [rbp+18h]
  _DWORD *v25; // [rsp+B8h] [rbp+20h]

  v2 = operator new[](0x18u, (const struct std::nothrow_t *)&std::nothrow);
  try
  {
    v3 = v2;
    v23 = v2;
    if ( v2 )
    {
      v24 = v19;
      v20 = 0;
      v4 = (__int64 (__fastcall ***)(_QWORD, _BYTE *))a1[7];
      if ( v4 )
        v20 = (_BYTE *)(**v4)(v4, v19);
      v24 = v19;
      *v3 = &CGenericWorkItem::`vftable';
      v3[1] = 0;
      v3[2] = 0;
      ProcessHeap = GetProcessHeap();
      v6 = HeapAlloc(ProcessHeap, 0, 0x50u);
      v7 = v6;
      v25 = v6;
      if ( v6 )
      {
        *(_OWORD *)v6 = 0;
        v6[2] = 1;
        v6[3] = 1;
        *(_QWORD *)v6 = &std::_Ref_count_obj2<std::function<void (void)>>::`vftable';
        v18 = (_DWORD)v6 + 16;
        *((_QWORD *)v6 + 9) = 0;
        if ( v20 )
          *((_QWORD *)v6 + 9) = (**(__int64 (__fastcall ***)(_BYTE *, __int64))v20)(v20, (__int64)(v6 + 4));
      }
      else
      {
        v7 = 0;
      }
      v3[1] = v7 + 4;
      v8 = (volatile signed __int32 *)v3[2];
      v3[2] = v7;
      if ( v8 )
      {
        if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
          if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
        }
      }
      if ( v20 )
      {
        v9 = v19;
        LOBYTE(v9) = v20 != v19;
        (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v20 + 32LL))(v20, v9);
        v20 = 0;
      }
    }
    else
    {
      v3 = 0;
    }
    v23 = v3;
    if ( v3 )
    {
      if ( PostQueuedCompletionStatus(g_WorkerEventPort, 0, (ULONG_PTR)v3, 0) )
        goto LABEL_22;
      LastError = GetLastError();
      v16 = LastError;
      if ( LastError > 0 )
        v16 = (unsigned __int16)LastError | 0x80070000;
      if ( (v16 & 0x80000000) == 0 )
      {
LABEL_22:
        v17 = (__int64 *)a1[7];
        if ( v17 )
        {
          LOBYTE(v14) = v17 != a1;
          (*(void (__fastcall **)(__int64 *, __int64))(*v17 + 32))(v17, v14);
          a1[7] = 0;
        }
        result = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x156,
          (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\workitem.cpp",
          (const char *)v16,
          v18);
        std::unique_ptr<CGenericWorkItem>::~unique_ptr<CGenericWorkItem>(&v23);
        std::_Func_class<void,>::~_Func_class<void,>(a1);
        result = v16;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x154,
        (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\workitem.cpp",
        (const char *)0x8007000ELL,
        v18);
      v11 = (__int64 *)a1[7];
      if ( v11 )
      {
        v12 = *v11;
        LOBYTE(v12) = v11 != a1;
        (*(void (__fastcall **)(__int64 *, __int64))(*v11 + 32))(v11, v12);
        a1[7] = 0;
      }
      result = 2147942414LL;
    }
  }
  catch ( ... )
  {
    LODWORD(v23) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x15C,
                     (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\workitem.cpp",
                     v10);
    std::_Func_class<void,>::~_Func_class<void,>(a1);
    return (unsigned int)v23;
  }
  return result;
}

```

## disassembly

```asm
0x180008e00  mov     [rsp+arg_0], rcx
0x180008e05  push    rbx
0x180008e06  push    rsi
0x180008e07  push    rdi
0x180008e08  push    r14
0x180008e0a  push    r15
0x180008e0c  sub     rsp, 70h
0x180008e10  mov     r14, rcx
0x180008e13  xor     r15d, r15d
0x180008e16  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180008e1d  mov     ecx, 18h; unsigned __int64
0x180008e22  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180008e27  mov     rbx, rax
0x180008e2a  mov     [rsp+98h+arg_8], rax
0x180008e32  test    rax, rax
0x180008e35  jz      loc_180009019
0x180008e3b  lea     rax, [rsp+98h+var_70]
0x180008e40  mov     [rsp+98h+arg_10], rax
0x180008e48  mov     [rsp+98h+var_38], r15
0x180008e4d  mov     rcx, [r14+38h]
0x180008e51  test    rcx, rcx
0x180008e54  jz      short loc_180008E6B
0x180008e56  mov     rax, [rcx]
0x180008e59  lea     rdx, [rsp+98h+var_70]
0x180008e5e  mov     rax, [rax]
0x180008e61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e66  mov     [rsp+98h+var_38], rax
0x180008e6b  lea     rax, [rsp+98h+var_70]
0x180008e70  mov     [rsp+98h+arg_10], rax
0x180008e78  lea     rax, ??_7CGenericWorkItem@@6B@; const CGenericWorkItem::`vftable'
0x180008e7f  mov     [rbx], rax
0x180008e82  mov     [rbx+8], r15
0x180008e86  mov     [rbx+10h], r15
0x180008e8a  call    cs:__imp_GetProcessHeap
0x180008e90  mov     rcx, rax; hHeap
0x180008e93  xor     edx, edx; dwFlags
0x180008e95  mov     r8d, 50h ; 'P'; dwBytes
0x180008e9b  call    cs:__imp_HeapAlloc
0x180008ea1  mov     rdi, rax
0x180008ea4  mov     [rsp+98h+arg_18], rax
0x180008eac  test    rax, rax
0x180008eaf  jz      loc_18000902C
0x180008eb5  xorps   xmm0, xmm0
0x180008eb8  movups  xmmword ptr [rax], xmm0
0x180008ebb  mov     dword ptr [rax+8], 1
0x180008ec2  mov     dword ptr [rax+0Ch], 1
0x180008ec9  lea     rax, ??_7?$_Ref_count_obj2@V?$function@$$A6AXXZ@std@@@std@@6B@; const std::_Ref_count_obj2<std::function<void (void)>>::`vftable'
0x180008ed0  mov     [rdi], rax
0x180008ed3  lea     rsi, [rdi+10h]
0x180008ed7  mov     qword ptr [rsp+98h+var_78], rsi; int
0x180008edc  mov     [rsi+38h], r15
0x180008ee0  mov     rcx, [rsp+98h+var_38]
0x180008ee5  test    rcx, rcx
0x180008ee8  jz      short loc_180008EFC
0x180008eea  mov     rax, [rcx]
0x180008eed  mov     rdx, rsi
0x180008ef0  mov     rax, [rax]
0x180008ef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ef8  mov     [rsi+38h], rax
0x180008efc  lea     rax, [rdi+10h]
0x180008f00  mov     [rbx+8], rax
0x180008f04  mov     rsi, [rbx+10h]
0x180008f08  mov     [rbx+10h], rdi
0x180008f0c  test    rsi, rsi
0x180008f0f  jz      short loc_180008F4A
0x180008f11  mov     edi, 0FFFFFFFFh
0x180008f16  mov     eax, edi
0x180008f18  lock xadd [rsi+8], eax
0x180008f1d  cmp     eax, 1
0x180008f20  jnz     short loc_180008F4A
0x180008f22  mov     rax, [rsi]
0x180008f25  mov     rcx, rsi
0x180008f28  mov     rax, [rax]
0x180008f2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f30  lock xadd [rsi+0Ch], edi
0x180008f35  cmp     edi, 1
0x180008f38  jnz     short loc_180008F4A
0x180008f3a  mov     rax, [rsi]
0x180008f3d  mov     rcx, rsi
0x180008f40  mov     rax, [rax+8]
0x180008f44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f49  nop
0x180008f4a  mov     rcx, [rsp+98h+var_38]
0x180008f4f  test    rcx, rcx
0x180008f52  jz      short loc_180008F70
0x180008f54  mov     rax, [rcx]
0x180008f57  lea     rdx, [rsp+98h+var_70]
0x180008f5c  cmp     rcx, rdx
0x180008f5f  setnz   dl
0x180008f62  mov     rax, [rax+20h]
0x180008f66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f6b  mov     [rsp+98h+var_38], r15
0x180008f70  mov     [rsp+98h+arg_8], rbx
0x180008f78  test    rbx, rbx
0x180008f7b  jnz     short loc_180008FC3
0x180008f7d  mov     rcx, [rsp+98h]; this
0x180008f85  mov     r9d, 8007000Eh; char *
0x180008f8b  lea     r8, aClientcoreMult_3; "clientcore\\multimedia\\audiocore\\serv"...
0x180008f92  mov     edx, 154h; void *
0x180008f97  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008f9c  nop
0x180008f9d  mov     rcx, [r14+38h]
0x180008fa1  test    rcx, rcx
0x180008fa4  jz      short loc_180008FBC
0x180008fa6  mov     rdx, [rcx]
0x180008fa9  mov     rax, [rdx+20h]
0x180008fad  cmp     rcx, r14
0x180008fb0  setnz   dl
0x180008fb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fb8  mov     [r14+38h], r15
0x180008fbc  mov     eax, 8007000Eh
0x180008fc1  jmp     short loc_18000900D
0x180008fc3  xor     r9d, r9d; lpOverlapped
0x180008fc6  mov     r8, rbx; dwCompletionKey
0x180008fc9  xor     edx, edx; dwNumberOfBytesTransferred
0x180008fcb  mov     rcx, cs:?g_WorkerEventPort@@3PEAXEA; CompletionPort
0x180008fd2  call    cs:__imp_PostQueuedCompletionStatus
0x180008fd8  test    eax, eax
0x180008fda  jnz     short loc_180008FEC
0x180008fdc  call    cs:__imp_GetLastError
0x180008fe2  mov     ebx, eax
0x180008fe4  test    eax, eax
0x180008fe6  jg      short loc_180009021
0x180008fe8  test    ebx, ebx
0x180008fea  js      short loc_180009034
0x180008fec  mov     rcx, [r14+38h]
0x180008ff0  test    rcx, rcx
0x180008ff3  jz      short loc_18000900B
0x180008ff5  mov     rax, [rcx]
0x180008ff8  cmp     rcx, r14
0x180008ffb  setnz   dl
0x180008ffe  mov     rax, [rax+20h]
0x180009002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009007  mov     [r14+38h], r15
0x18000900b  xor     eax, eax
0x18000900d  add     rsp, 70h
0x180009011  pop     r15
0x180009013  pop     r14
0x180009015  pop     rdi
0x180009016  pop     rsi
0x180009017  pop     rbx
0x180009018  retn
0x180009019  mov     rbx, r15
0x18000901c  jmp     loc_180008F70
0x180009021  movzx   ebx, ax
0x180009024  or      ebx, 80070000h
0x18000902a  jmp     short loc_180008FE8
0x18000902c  mov     rdi, r15
0x18000902f  jmp     loc_180008EFC
0x180009034  mov     rcx, [rsp+98h]; this
0x18000903c  mov     r9d, ebx; char *
0x18000903f  lea     r8, aClientcoreMult_3; "clientcore\\multimedia\\audiocore\\serv"...
0x180009046  mov     edx, 156h; void *
0x18000904b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009050  lea     rcx, [rsp+98h+arg_8]
0x180009058  call    ??1?$unique_ptr@VCGenericWorkItem@@U?$default_delete@VCGenericWorkItem@@@std@@@std@@QEAA@XZ; std::unique_ptr<CGenericWorkItem>::~unique_ptr<CGenericWorkItem>(void)
0x18000905d  nop
0x18000905e  mov     rcx, r14
0x180009061  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x180009066  mov     eax, ebx
0x180009068  jmp     short loc_18000900D
0x18000906a  mov     rcx, [rsp+98h+arg_0]
0x180009072  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x180009077  mov     eax, dword ptr [rsp+98h+arg_8]
0x18000907e  jmp     short loc_18000900D
```
