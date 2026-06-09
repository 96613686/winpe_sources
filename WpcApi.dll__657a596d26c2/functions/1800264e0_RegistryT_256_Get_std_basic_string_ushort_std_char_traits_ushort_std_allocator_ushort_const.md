# RegistryT<256>::Get(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800264e0`
- end: `0x18002659b`
- name: `?Get@?$RegistryT@$0BAA@@@UEAA?AV?$unique_ref@UIStorageValue@@U?$default_delete@UIStorageValue@@@std@@@stdext@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `187`
- prototype: `__int64 *__fastcall(__int64, __int64 *, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x1800032c4`
- `0x180003d20`
- `0x180005a04`
- `0x1800195c4`
- `0x18002506c`
- `0x1800264e0`

## pseudocode

```c
__int64 *__fastcall RegistryT<256>::Get(__int64 a1, __int64 *a2, __int64 a3)
{
  __int64 *v6; // rsi
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rax
  __int128 v11; // [rsp+38h] [rbp-38h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+48h] [rbp-28h] BYREF
  __int64 v13; // [rsp+A0h] [rbp+30h] BYREF
  __int64 *v14; // [rsp+A8h] [rbp+38h]
  __int64 *v15; // [rsp+B8h] [rbp+48h]

  v14 = a2;
  v6 = (__int64 *)operator new(0x50u);
  v15 = v6;
  v11 = 0;
  v7 = *(_QWORD *)(a1 + 24);
  if ( v7 )
    _InterlockedIncrement((volatile signed __int32 *)(v7 + 8));
  v11 = *(_OWORD *)(a1 + 16);
  v8 = std::wstring::wstring((__int64)pExceptionObject, a3);
  v9 = anonymous_namespace_::StorageValue_256_::StorageValue_256_(v6, v8, &v11);
  v15 = &v13;
  v13 = 0;
  *a2 = v9;
  if ( !v9 )
  {
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, -2147418113);
    throw (ErrorCodeException *)pExceptionObject;
  }
  return a2;
}

```

## disassembly

```asm
0x1800264e0  mov     [rsp-28h+arg_8], rdx
0x1800264e5  push    rbp
0x1800264e6  push    rbx
0x1800264e7  push    rsi
0x1800264e8  push    rdi
0x1800264e9  push    r14
0x1800264eb  mov     rbp, rsp
0x1800264ee  sub     rsp, 70h
0x1800264f2  mov     r14, r8
0x1800264f5  mov     rbx, rdx
0x1800264f8  mov     rdi, rcx
0x1800264fb  mov     ecx, 50h ; 'P'; Size
0x180026500  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026505  mov     rsi, rax
0x180026508  mov     [rbp+arg_18], rax
0x18002650c  lea     rax, [rbp+var_38]
0x180026510  mov     [rbp+var_48], rax
0x180026514  xorps   xmm0, xmm0
0x180026517  movdqu  [rbp+var_38], xmm0
0x18002651c  mov     rcx, [rdi+18h]
0x180026520  test    rcx, rcx
0x180026523  jz      short loc_180026529
0x180026525  lock inc dword ptr [rcx+8]
0x180026529  mov     rax, [rdi+10h]
0x18002652d  mov     qword ptr [rbp+var_38], rax
0x180026531  mov     rax, [rdi+18h]
0x180026535  mov     qword ptr [rbp+var_38+8], rax
0x180026539  mov     rdx, r14
0x18002653c  lea     rcx, [rbp+pExceptionObject]
0x180026540  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180026545  nop
0x180026546  lea     r8, [rbp+var_38]
0x18002654a  mov     rdx, rax
0x18002654d  mov     rcx, rsi
0x180026550  call    _anonymous_namespace___StorageValue_256___StorageValue_256_
0x180026555  nop
0x180026556  lea     rcx, [rbp+arg_0]
0x18002655a  mov     [rbp+arg_18], rcx
0x18002655e  mov     [rbp+arg_0], 0
0x180026566  mov     [rbx], rax
0x180026569  test    rax, rax
0x18002656c  jz      short loc_18002657C
0x18002656e  mov     rax, rbx
0x180026571  add     rsp, 70h
0x180026575  pop     r14
0x180026577  pop     rdi
0x180026578  pop     rsi
0x180026579  pop     rbx
0x18002657a  pop     rbp
0x18002657b  retn
0x18002657c  mov     edx, 8000FFFFh; int
0x180026581  lea     rcx, [rbp+pExceptionObject]; this
0x180026585  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x18002658a  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x180026591  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180026595  call    _CxxThrowException_0
```
