# sub_1800A7DBC

- ea: `0x1800a7dbc`
- end: `0x1800a7ecb`
- name: `sub_1800A7DBC`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800a70f0`

## callees

- `0x180006ff0`
- `0x180032960`
- `0x1800a6a20`
- `0x1800a70c4`
- `0x1800a7604`
- `0x1800a7dbc`
- `0x1800f9010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800a7dde`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800a7dde`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a7df6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a7df6`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800a7e12`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800a7e12`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPVOID __fastcall sub_1800A7DBC(__int64 a1, char a2)
{
  LPVOID result; // rax
  signed __int32 v5; // ebx
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // [rsp+20h] [rbp-78h] BYREF
  _BYTE v9[16]; // [rsp+30h] [rbp-68h] BYREF
  _OWORD pExceptionObject[2]; // [rsp+40h] [rbp-58h] BYREF
  __int64 v11; // [rsp+60h] [rbp-38h]

  if ( !byte_1801C5110 )
  {
    if ( off_18015D000 != (_UNKNOWN *)&off_18015D000 && (*((_BYTE *)off_18015D000 + 28) & 1) != 0 )
      sub_180032960(*((_QWORD *)off_18015D000 + 2), 19, qword_18010C8A8);
    memset(pExceptionObject, 0, sizeof(pExceptionObject));
    v11 = 0;
    sub_1800A70C4(pExceptionObject);
    throw (ThreadCancelledException *)pExceptionObject;
  }
  result = TlsGetValue(dword_1801C3FA0);
  if ( !result )
  {
    v5 = _InterlockedIncrement(&dword_1801C3E58);
    *(_DWORD *)(a1 + 72) = GetCurrentThreadId();
    *(_DWORD *)(a1 + 76) = v5;
    *(_BYTE *)(a1 + 80) = a2;
    TlsSetValue(dword_1801C3FA0, (LPVOID)(a1 + 72));
    v6 = sub_1800A7604();
    v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v6 + 48LL))(v6, &v8);
    result = (LPVOID)sub_1800A6A20(*(_QWORD *)(v7 + 8), v9, a1 + 72);
    *(_QWORD *)(*(_QWORD *)result + 24LL) = a1 + 72;
    if ( v8 )
      return (LPVOID)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 24LL))(v8);
  }
  return result;
}

```

## disassembly

```asm
0x1800a7dbc  push    rbx
0x1800a7dbe  push    rbp
0x1800a7dbf  push    rsi
0x1800a7dc0  push    rdi
0x1800a7dc1  sub     rsp, 78h
0x1800a7dc5  mov     bpl, dl
0x1800a7dc8  mov     rsi, rcx
0x1800a7dcb  cmp     cs:byte_1801C5110, 0
0x1800a7dd2  jz      loc_1800A7E6D
0x1800a7dd8  mov     ecx, cs:dword_1801C3FA0; dwTlsIndex
0x1800a7dde  call    cs:TlsGetValue
0x1800a7de4  test    rax, rax
0x1800a7de7  jnz     short loc_1800A7E64
0x1800a7de9  lea     ebx, [rax+1]
0x1800a7dec  lock xadd cs:dword_1801C3E58, ebx
0x1800a7df4  inc     ebx
0x1800a7df6  call    cs:GetCurrentThreadId
0x1800a7dfc  lea     rdi, [rsi+48h]
0x1800a7e00  mov     [rdi], eax
0x1800a7e02  mov     [rdi+4], ebx
0x1800a7e05  mov     [rsi+50h], bpl
0x1800a7e09  mov     rdx, rdi; lpTlsValue
0x1800a7e0c  mov     ecx, cs:dword_1801C3FA0; dwTlsIndex
0x1800a7e12  call    cs:TlsSetValue
0x1800a7e18  call    sub_1800A7604
0x1800a7e1d  mov     r8, rax
0x1800a7e20  mov     rcx, [rax]
0x1800a7e23  mov     rax, [rcx+30h]
0x1800a7e27  lea     rdx, [rsp+98h+var_78]
0x1800a7e2c  mov     rcx, r8
0x1800a7e2f  call    j__guard_dispatch_icall
0x1800a7e34  nop
0x1800a7e35  mov     r8, rdi
0x1800a7e38  lea     rdx, [rsp+98h+var_68]
0x1800a7e3d  mov     rcx, [rax+8]
0x1800a7e41  call    sub_1800A6A20
0x1800a7e46  mov     rcx, [rax]
0x1800a7e49  mov     [rcx+18h], rdi
0x1800a7e4d  mov     rcx, [rsp+98h+var_78]
0x1800a7e52  test    rcx, rcx
0x1800a7e55  jz      short loc_1800A7E64
0x1800a7e57  mov     rax, [rcx]
0x1800a7e5a  mov     rax, [rax+18h]
0x1800a7e5e  call    j__guard_dispatch_icall
0x1800a7e63  nop
0x1800a7e64  add     rsp, 78h
0x1800a7e68  pop     rdi
0x1800a7e69  pop     rsi
0x1800a7e6a  pop     rbp
0x1800a7e6b  pop     rbx
0x1800a7e6c  retn
0x1800a7e6d  lea     rax, off_18015D000
0x1800a7e74  mov     rcx, cs:off_18015D000
0x1800a7e7b  cmp     rcx, rax
0x1800a7e7e  jz      short loc_1800A7E9B
0x1800a7e80  test    byte ptr [rcx+1Ch], 1
0x1800a7e84  jz      short loc_1800A7E9B
0x1800a7e86  mov     edx, 13h
0x1800a7e8b  lea     r8, qword_18010C8A8
0x1800a7e92  mov     rcx, [rcx+10h]
0x1800a7e96  call    sub_180032960
0x1800a7e9b  xorps   xmm0, xmm0
0x1800a7e9e  xor     eax, eax
0x1800a7ea0  movups  [rsp+98h+pExceptionObject], xmm0
0x1800a7ea5  movups  [rsp+98h+var_48], xmm0
0x1800a7eaa  mov     [rsp+98h+var_38], rax
0x1800a7eaf  lea     rcx, [rsp+98h+pExceptionObject]
0x1800a7eb4  call    sub_1800A70C4
0x1800a7eb9  lea     rdx, __TI4?AVThreadCancelledException@@; pThrowInfo
0x1800a7ec0  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x1800a7ec5  call    _CxxThrowException
```
