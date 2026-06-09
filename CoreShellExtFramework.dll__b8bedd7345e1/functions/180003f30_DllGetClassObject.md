# DllGetClassObject

- ea: `0x180003f30`
- end: `0x180004162`
- name: `DllGetClassObject`
- size: `562`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003f30`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180004053`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180004066`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180004053`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180004066`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800040ff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800040ff`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800040b6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800040b6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180004011`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180004011`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180004023`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800040df`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180004023`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800040df`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800040d0`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800040d0`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180003f5d`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180003f5d`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  unsigned __int64 v6; // rbx
  unsigned __int64 v7; // rax
  _QWORD *v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rbx
  RTL_SRWLOCK *v11; // rsi
  void *v12; // rcx
  HRESULT v13; // edi
  RTL_SRWLOCK *v14; // rsi
  void *v15; // rcx
  PVOID v16; // rdi
  int v18; // [rsp+70h] [rbp+18h] BYREF
  PVOID Ptr; // [rsp+78h] [rbp+20h] BYREF

  InitOnceExecuteOnce(&InitOnce, InitFn, 0, 0);
  byte_18001F5B0 = 1;
  *ppv = 0;
  v6 = (*(__int64 (__fastcall **)(__int64 *))(qword_18001F5A8 + 32))(&qword_18001F5A8) + 8;
  v7 = (*(__int64 (__fastcall **)(__int64 *))(qword_18001F5A8 + 40))(&qword_18001F5A8);
  while ( v6 < v7 )
  {
    if ( *(_QWORD *)v6 )
    {
      v8 = *(_QWORD **)(*(_QWORD *)v6 + 8LL);
      v9 = *v8 - *(_QWORD *)&rclsid->Data1;
      if ( *v8 == *(_QWORD *)&rclsid->Data1 )
        v9 = v8[1] - *(_QWORD *)rclsid->Data4;
      if ( !v9 )
      {
        _mm_lfence();
        v18 = 1;
        v10 = *(_QWORD *)v6;
        *ppv = 0;
        Ptr = 0;
        if ( **(_QWORD **)(v10 + 24) )
        {
          v11 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(__int64 *))(qword_18001F5A8 + 56))(&qword_18001F5A8);
          AcquireSRWLockShared(v11);
          v12 = **(void ***)(v10 + 24);
          if ( v12 )
          {
            Ptr = DecodePointer(v12);
            v13 = (**(__int64 (__fastcall ***)(PVOID, const IID *const, LPVOID *))Ptr)(Ptr, riid, ppv);
            if ( v11 )
              ReleaseSRWLockShared(v11);
            return v13;
          }
          if ( v11 )
            ReleaseSRWLockShared(v11);
        }
        v13 = (*(__int64 (__fastcall **)(int *, __int64, const IID *const, PVOID *))v10)(&v18, v10, riid, &Ptr);
        if ( v13 >= 0 )
        {
          if ( (v18 & 4) != 0 )
            goto LABEL_23;
          v14 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(__int64 *))(qword_18001F5A8 + 56))(&qword_18001F5A8);
          AcquireSRWLockExclusive(v14);
          v15 = **(void ***)(v10 + 24);
          if ( v15 )
          {
            v16 = DecodePointer(v15);
            (*(void (__fastcall **)(PVOID))(*(_QWORD *)v16 + 8LL))(v16);
          }
          else
          {
            v16 = 0;
            **(_QWORD **)(v10 + 24) = EncodePointer(Ptr);
          }
          if ( v14 )
            ReleaseSRWLockExclusive(v14);
          if ( !v16 )
          {
LABEL_23:
            v16 = Ptr;
          }
          else
          {
            (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 16LL))(Ptr);
            (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 16LL))(Ptr);
          }
          *ppv = v16;
          return 0;
        }
        return v13;
      }
    }
    v6 += 8LL;
  }
  return -2147221231;
}

```

## disassembly

```asm
0x180003f30  mov     [rsp+arg_0], rbx
0x180003f35  push    rbp
0x180003f36  push    rsi
0x180003f37  push    rdi
0x180003f38  push    r14
0x180003f3a  push    r15
0x180003f3c  sub     rsp, 30h
0x180003f40  mov     r14, r8
0x180003f43  mov     rbp, rdx
0x180003f46  mov     rdi, rcx
0x180003f49  xor     r9d, r9d; Context
0x180003f4c  xor     r8d, r8d; Parameter
0x180003f4f  lea     rdx, InitFn; InitFn
0x180003f56  lea     rcx, InitOnce; InitOnce
0x180003f5d  call    cs:InitOnceExecuteOnce
0x180003f63  mov     cs:byte_18001F5B0, 1
0x180003f6a  xor     r15d, r15d
0x180003f6d  mov     [r14], r15
0x180003f70  mov     rax, cs:qword_18001F5A8
0x180003f77  lea     rcx, qword_18001F5A8
0x180003f7e  mov     rax, [rax+20h]
0x180003f82  call    j__guard_dispatch_icall
0x180003f87  lea     rbx, [rax+8]
0x180003f8b  mov     rcx, cs:qword_18001F5A8
0x180003f92  mov     rax, [rcx+28h]
0x180003f96  lea     rcx, qword_18001F5A8
0x180003f9d  call    j__guard_dispatch_icall
0x180003fa2  cmp     rbx, rax
0x180003fa5  jnb     loc_18000414C
0x180003fab  mov     rcx, [rbx]
0x180003fae  test    rcx, rcx
0x180003fb1  jz      short loc_180003FCC
0x180003fb3  mov     rdx, [rcx+8]
0x180003fb7  mov     rcx, [rdx]
0x180003fba  sub     rcx, [rdi]
0x180003fbd  jnz     short loc_180003FC7
0x180003fbf  mov     rcx, [rdx+8]
0x180003fc3  sub     rcx, [rdi+8]
0x180003fc7  test    rcx, rcx
0x180003fca  jz      short loc_180003FD2
0x180003fcc  add     rbx, 8
0x180003fd0  jmp     short loc_180003FA2
0x180003fd2  lfence
0x180003fd5  mov     [rsp+58h+arg_10], 1
0x180003fdd  mov     rbx, [rbx]
0x180003fe0  mov     [r14], r15
0x180003fe3  mov     [rsp+58h+Ptr], r15
0x180003fe8  mov     rax, [rbx+18h]
0x180003fec  mov     rcx, [rax]
0x180003fef  test    rcx, rcx
0x180003ff2  jz      short loc_18000406C
0x180003ff4  mov     rax, cs:qword_18001F5A8
0x180003ffb  lea     rcx, qword_18001F5A8
0x180004002  mov     rax, [rax+38h]
0x180004006  call    j__guard_dispatch_icall
0x18000400b  mov     rsi, rax
0x18000400e  mov     rcx, rax; SRWLock
0x180004011  call    cs:AcquireSRWLockShared
0x180004017  mov     rcx, [rbx+18h]
0x18000401b  mov     rcx, [rcx]; Ptr
0x18000401e  test    rcx, rcx
0x180004021  jz      short loc_18000405E
0x180004023  call    cs:DecodePointer
0x180004029  mov     r9, rax
0x18000402c  mov     [rsp+58h+Ptr], rax
0x180004031  mov     rcx, [rax]
0x180004034  mov     rax, [rcx]
0x180004037  mov     r8, r14
0x18000403a  mov     rdx, rbp
0x18000403d  mov     rcx, r9
0x180004040  call    j__guard_dispatch_icall
0x180004045  mov     edi, eax
0x180004047  test    rsi, rsi
0x18000404a  jz      loc_180004139
0x180004050  mov     rcx, rsi; SRWLock
0x180004053  call    cs:ReleaseSRWLockShared
0x180004059  jmp     loc_180004139
0x18000405e  test    rsi, rsi
0x180004061  jz      short loc_18000406C
0x180004063  mov     rcx, rsi; SRWLock
0x180004066  call    cs:ReleaseSRWLockShared
0x18000406c  lea     r9, [rsp+58h+Ptr]
0x180004071  mov     r8, rbp
0x180004074  mov     rdx, rbx
0x180004077  lea     rcx, [rsp+58h+arg_10]
0x18000407c  mov     rax, [rbx]
0x18000407f  call    j__guard_dispatch_icall
0x180004084  mov     edi, eax
0x180004086  test    eax, eax
0x180004088  js      loc_180004139
0x18000408e  test    byte ptr [rsp+58h+arg_10], 4
0x180004093  jnz     loc_18000412E
0x180004099  mov     rax, cs:qword_18001F5A8
0x1800040a0  lea     rcx, qword_18001F5A8
0x1800040a7  mov     rax, [rax+38h]
0x1800040ab  call    j__guard_dispatch_icall
0x1800040b0  mov     rsi, rax
0x1800040b3  mov     rcx, rax; SRWLock
0x1800040b6  call    cs:AcquireSRWLockExclusive
0x1800040bc  mov     rcx, [rbx+18h]
0x1800040c0  mov     rcx, [rcx]; Ptr
0x1800040c3  test    rcx, rcx
0x1800040c6  jnz     short loc_1800040DF
0x1800040c8  mov     rdi, r15
0x1800040cb  mov     rcx, [rsp+58h+Ptr]; Ptr
0x1800040d0  call    cs:EncodePointer
0x1800040d6  mov     rcx, [rbx+18h]
0x1800040da  mov     [rcx], rax
0x1800040dd  jmp     short loc_1800040F7
0x1800040df  call    cs:DecodePointer
0x1800040e5  mov     rdi, rax
0x1800040e8  mov     rcx, [rax]
0x1800040eb  mov     rax, [rcx+8]
0x1800040ef  mov     rcx, rdi
0x1800040f2  call    j__guard_dispatch_icall
0x1800040f7  test    rsi, rsi
0x1800040fa  jz      short loc_180004105
0x1800040fc  mov     rcx, rsi; SRWLock
0x1800040ff  call    cs:ReleaseSRWLockExclusive
0x180004105  test    rdi, rdi
0x180004108  jz      short loc_18000412E
0x18000410a  mov     rcx, [rsp+58h+Ptr]
0x18000410f  mov     rax, [rcx]
0x180004112  mov     rax, [rax+10h]
0x180004116  call    j__guard_dispatch_icall
0x18000411b  mov     rcx, [rsp+58h+Ptr]
0x180004120  mov     rax, [rcx]
0x180004123  mov     rax, [rax+10h]
0x180004127  call    j__guard_dispatch_icall
0x18000412c  jmp     short loc_180004133
0x18000412e  mov     rdi, [rsp+58h+Ptr]
0x180004133  mov     [r14], rdi
0x180004136  mov     edi, r15d
0x180004139  mov     eax, edi
0x18000413b  mov     rbx, [rsp+58h+arg_0]
0x180004140  add     rsp, 30h
0x180004144  pop     r15
0x180004146  pop     r14
0x180004148  pop     rdi
0x180004149  pop     rsi
0x18000414a  pop     rbp
0x18000414b  retn
0x18000414c  mov     eax, 80040111h
0x180004151  mov     rbx, [rsp+58h+arg_0]
0x180004156  add     rsp, 30h
0x18000415a  pop     r15
0x18000415c  pop     r14
0x18000415e  pop     rdi
0x18000415f  pop     rsi
0x180004160  pop     rbp
0x180004161  retn
```
