# CReader::AvailabilityStatus(void)

- ea: `0x18000cd80`
- end: `0x18000cf53`
- name: `?AvailabilityStatus@CReader@@QEAA?AW4AvailableState@1@XZ`
- size: `467`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `10`
- callee_count: `5`
- tags: ``

## callers

- `0x1800016e0`
- `0x180001950`
- `0x18000371c`
- `0x18000a310`
- `0x18000ecb0`
- `0x1800140f0`
- `0x180018f84`
- `0x18002a414`
- `0x18002a504`
- `0x18002dbd8`

## callees

- `0x18000c870`
- `0x18000cd80`
- `0x18000fb50`
- `0x18003261b`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000ce2b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000ce2b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000ce7f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000ce7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cf1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cf37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cf1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cf37`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000cdb2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000cddc`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000cef6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000cdb2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000cddc`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000cef6`

## pseudocode

```c
__int64 __fastcall CReader::AvailabilityStatus(__int64 a1)
{
  __int64 v2; // rbx
  __int64 v3; // rdi
  LPVOID Value; // rsi
  unsigned int v5; // eax
  unsigned int v6; // edi
  bool v7; // zf
  __int64 pExceptionObject; // [rsp+40h] [rbp+8h] BYREF
  __int64 v10; // [rsp+48h] [rbp+10h]

  v2 = a1 + 56;
  pExceptionObject = a1 + 56;
  (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))(a1 + 56))(a1 + 56, 0, 0);
  if ( *(LPVOID *)(v2 + 104) == TlsGetValue(dwTlsIndex) )
  {
    ++*(_DWORD *)(v2 + 56);
    CAccessLock::UnsignalNoReaders((CAccessLock *)v2);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
  }
  else
  {
    do
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
      v3 = *(_QWORD *)(v2 + 88);
      Value = TlsGetValue(dword_18004B240);
      while ( 1 )
      {
        v5 = WaitForAnyObject(0xFFFFFFFF, v3, Value, 0);
        if ( v5 == 1 )
          break;
        if ( v5 == 2 )
        {
          LODWORD(pExceptionObject) = -2146435070;
          throw (ulong *)&pExceptionObject;
        }
      }
      v10 = v2;
      (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))v2)(v2, 0, 0);
    }
    while ( *(_DWORD *)(v2 + 60) && *(LPVOID *)(v2 + 104) != TlsGetValue(dwTlsIndex) );
    ++*(_DWORD *)(v2 + 56);
    if ( !ResetEvent(*(HANDLE *)(v2 + 72)) )
    {
      LODWORD(pExceptionObject) = GetLastError();
      throw (ulong *)&pExceptionObject;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
  }
  v6 = *(_DWORD *)(a1 + 192);
  if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2) )
  {
    (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))v2)(v2, 0, 0);
    v7 = (*(_DWORD *)(v2 + 56))-- == 1;
    if ( v7 && !SetEvent(*(HANDLE *)(v2 + 72)) )
    {
      LODWORD(pExceptionObject) = GetLastError();
      throw (ulong *)&pExceptionObject;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
  }
  return v6;
}

```

## disassembly

```asm
0x18000cd80  mov     [rsp+arg_10], rbx
0x18000cd85  push    rbp
0x18000cd86  push    rsi
0x18000cd87  push    rdi
0x18000cd88  sub     rsp, 20h
0x18000cd8c  mov     rbp, rcx
0x18000cd8f  lea     rbx, [rcx+38h]
0x18000cd93  mov     [rsp+38h+pExceptionObject], rbx
0x18000cd98  mov     rax, [rbx]
0x18000cd9b  xor     r8d, r8d
0x18000cd9e  xor     edx, edx
0x18000cda0  mov     rcx, rbx
0x18000cda3  mov     rax, [rax]
0x18000cda6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdab  nop
0x18000cdac  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18000cdb2  call    cs:__imp_TlsGetValue
0x18000cdb8  cmp     [rbx+68h], rax
0x18000cdbc  jz      loc_18000CECF
0x18000cdc2  mov     rax, [rbx]
0x18000cdc5  mov     rcx, rbx
0x18000cdc8  mov     rax, [rax+8]
0x18000cdcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdd1  nop
0x18000cdd2  mov     rdi, [rbx+58h]
0x18000cdd6  mov     ecx, cs:dword_18004B240; dwTlsIndex
0x18000cddc  call    cs:__imp_TlsGetValue
0x18000cde2  mov     rsi, rax
0x18000cde5  xor     r9d, r9d
0x18000cde8  mov     r8, rsi
0x18000cdeb  mov     rdx, rdi
0x18000cdee  mov     ecx, 0FFFFFFFFh; dwMilliseconds
0x18000cdf3  call    ?WaitForAnyObject@@YAKKZZ; WaitForAnyObject(ulong,...)
0x18000cdf8  cmp     eax, 1
0x18000cdfb  jnz     loc_18000CEAC
0x18000ce01  mov     [rsp+38h+arg_8], rbx
0x18000ce06  mov     rax, [rbx]
0x18000ce09  xor     r8d, r8d
0x18000ce0c  xor     edx, edx
0x18000ce0e  mov     rcx, rbx
0x18000ce11  mov     rax, [rax]
0x18000ce14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce19  nop
0x18000ce1a  cmp     dword ptr [rbx+3Ch], 0
0x18000ce1e  jnz     loc_18000CEF0
0x18000ce24  inc     dword ptr [rbx+38h]
0x18000ce27  mov     rcx, [rbx+48h]; hEvent
0x18000ce2b  call    cs:__imp_ResetEvent
0x18000ce31  test    eax, eax
0x18000ce33  jz      loc_18000CF1B
0x18000ce39  mov     rax, [rbx]
0x18000ce3c  mov     rcx, rbx
0x18000ce3f  mov     rax, [rax+8]
0x18000ce43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce48  nop
0x18000ce49  mov     edi, [rbp+0C0h]
0x18000ce4f  mov     rax, [rbx]
0x18000ce52  mov     rcx, rbx
0x18000ce55  mov     rax, [rax+10h]
0x18000ce59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce5e  test    eax, eax
0x18000ce60  jnz     short loc_18000CE9D
0x18000ce62  mov     rax, [rbx]
0x18000ce65  xor     r8d, r8d
0x18000ce68  xor     edx, edx
0x18000ce6a  mov     rcx, rbx
0x18000ce6d  mov     rax, [rax]
0x18000ce70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce75  add     dword ptr [rbx+38h], 0FFFFFFFFh
0x18000ce79  jnz     short loc_18000CE8D
0x18000ce7b  mov     rcx, [rbx+48h]; hEvent
0x18000ce7f  call    cs:__imp_SetEvent
0x18000ce85  test    eax, eax
0x18000ce87  jz      loc_18000CF37
0x18000ce8d  mov     rax, [rbx]
0x18000ce90  mov     rcx, rbx
0x18000ce93  mov     rax, [rax+8]
0x18000ce97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce9c  nop
0x18000ce9d  mov     eax, edi
0x18000ce9f  mov     rbx, [rsp+38h+arg_10]
0x18000cea4  add     rsp, 20h
0x18000cea8  pop     rdi
0x18000cea9  pop     rsi
0x18000ceaa  pop     rbp
0x18000ceab  retn
0x18000ceac  cmp     eax, 2
0x18000ceaf  jnz     loc_18000CDE5
0x18000ceb5  mov     dword ptr [rsp+38h+pExceptionObject], 80100002h
0x18000cebd  lea     rdx, _TI1K; pThrowInfo
0x18000cec4  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18000cec9  call    _CxxThrowException_0
0x18000cecf  inc     dword ptr [rbx+38h]
0x18000ced2  mov     rcx, rbx; this
0x18000ced5  call    ?UnsignalNoReaders@CAccessLock@@IEAAXXZ; CAccessLock::UnsignalNoReaders(void)
0x18000ceda  nop
0x18000cedb  mov     rax, [rbx]
0x18000cede  mov     rcx, rbx
0x18000cee1  mov     rax, [rax+8]
0x18000cee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ceea  nop
0x18000ceeb  jmp     loc_18000CE49
0x18000cef0  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18000cef6  call    cs:__imp_TlsGetValue
0x18000cefc  cmp     [rbx+68h], rax
0x18000cf00  jz      loc_18000CE24
0x18000cf06  mov     rax, [rbx]
0x18000cf09  mov     rcx, rbx
0x18000cf0c  mov     rax, [rax+8]
0x18000cf10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf15  nop
0x18000cf16  jmp     loc_18000CDD2
0x18000cf1b  call    cs:__imp_GetLastError
0x18000cf21  mov     dword ptr [rsp+38h+pExceptionObject], eax
0x18000cf25  lea     rdx, _TI1K; pThrowInfo
0x18000cf2c  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18000cf31  call    _CxxThrowException_0
0x18000cf37  call    cs:__imp_GetLastError
0x18000cf3d  mov     dword ptr [rsp+38h+pExceptionObject], eax
0x18000cf41  lea     rdx, _TI1K; pThrowInfo
0x18000cf48  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18000cf4d  call    _CxxThrowException_0
```
