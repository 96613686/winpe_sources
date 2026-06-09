# CHString::AssignCopy(int,ushort const *)

- ea: `0x140010810`
- end: `0x140010891`
- name: `?AssignCopy@CHString@@IEAAXHPEBG@Z`
- size: `129`
- prototype: `void __fastcall(const unsigned __int16 **this, int, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x14000ffc0`
- `0x140010070`
- `0x1400100a0`
- `0x140010190`

## callees

- `0x1400027e1`
- `0x1400105c0`
- `0x140010810`
- `0x1400115e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140010833`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140010833`

## pseudocode

```c
void __fastcall CHString::AssignCopy(const unsigned __int16 **this, int a2, const unsigned __int16 *a3)
{
  __int64 v3; // rdi
  char *v6; // rax

  v3 = a2;
  if ( a2 < 0 )
    RaiseException(0x57u, 1u, 0, 0);
  CHString::AllocBeforeWrite(this, v3);
  if ( (int)v3 <= 0 )
  {
    CHString::Release((CHString *)this);
  }
  else
  {
    memcpy_0((void *)*this, a3, 2 * v3);
    if ( *this == afxPchNil )
      v6 = byte_140024890;
    else
      v6 = (char *)(*this - 6);
    *((_DWORD *)v6 + 1) = v3;
    (*this)[v3] = 0;
  }
}

```

## disassembly

```asm
0x140010810  push    rbx
0x140010812  push    rbp
0x140010813  push    rsi
0x140010814  push    rdi
0x140010815  sub     rsp, 28h
0x140010819  movsxd  rdi, edx
0x14001081c  mov     rbp, r8
0x14001081f  mov     rbx, rcx
0x140010822  test    edx, edx
0x140010824  jns     short loc_140010839
0x140010826  xor     r9d, r9d; lpArguments
0x140010829  xor     r8d, r8d; nNumberOfArguments
0x14001082c  lea     edx, [r9+1]; dwExceptionFlags
0x140010830  lea     ecx, [rdx+56h]; dwExceptionCode
0x140010833  call    cs:__imp_RaiseException
0x140010839  mov     edx, edi; int
0x14001083b  mov     rcx, rbx; this
0x14001083e  call    ?AllocBeforeWrite@CHString@@IEAAXH@Z; CHString::AllocBeforeWrite(int)
0x140010843  test    edi, edi
0x140010845  jle     short loc_140010880
0x140010847  mov     rcx, [rbx]; void *
0x14001084a  lea     rsi, [rdi+rdi]
0x14001084e  mov     r8, rsi; Size
0x140010851  mov     rdx, rbp; Src
0x140010854  call    memcpy_0
0x140010859  mov     rax, [rbx]
0x14001085c  cmp     rax, cs:?afxPchNil@@3PEBGEB; ushort const * const afxPchNil
0x140010863  jnz     short loc_14001086E
0x140010865  lea     rax, byte_140024890
0x14001086c  jmp     short loc_140010872
0x14001086e  add     rax, 0FFFFFFFFFFFFFFF4h
0x140010872  mov     [rax+4], edi
0x140010875  xor     eax, eax
0x140010877  mov     rcx, [rbx]
0x14001087a  mov     [rsi+rcx], ax
0x14001087e  jmp     short loc_140010888
0x140010880  mov     rcx, rbx; this
0x140010883  call    ?Release@CHString@@QEAAXXZ; CHString::Release(void)
0x140010888  add     rsp, 28h
0x14001088c  pop     rdi
0x14001088d  pop     rsi
0x14001088e  pop     rbp
0x14001088f  pop     rbx
0x140010890  retn
```
