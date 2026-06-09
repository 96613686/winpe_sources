# ReadRegistryT<256>::Get(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180026404`
- end: `0x1800264d9`
- name: `?Get@?$ReadRegistryT@$0BAA@@@UEBA?AV?$unique_ref@UIConstStorageValue@@U?$default_delete@UIConstStorageValue@@@std@@@stdext@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `213`
- prototype: `__int64 *__fastcall(__int64, __int64 *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800263f0`

## callees

- `0x1800032c4`
- `0x180003d20`
- `0x180005a04`
- `0x1800195c4`
- `0x18002506c`
- `0x180026404`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall ReadRegistryT<256>::Get(__int64 a1, __int64 *a2, __int64 a3)
{
  __int64 *v6; // rsi
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rax
  __int128 v12; // [rsp+38h] [rbp-38h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+48h] [rbp-28h] BYREF
  __int64 v14; // [rsp+A0h] [rbp+30h] BYREF
  __int64 *v15; // [rsp+A8h] [rbp+38h]
  __int64 *v16; // [rsp+B8h] [rbp+48h]

  v15 = a2;
  v6 = (__int64 *)operator new(0x50u);
  v16 = v6;
  v12 = 0;
  v7 = *(_QWORD *)(a1 - 24);
  if ( v7 )
    _InterlockedIncrement((volatile signed __int32 *)(v7 + 8));
  v12 = *(_OWORD *)(a1 - 32);
  v8 = std::wstring::wstring((__int64)pExceptionObject, a3);
  v9 = anonymous_namespace_::StorageValue_256_::StorageValue_256_(v6, v8, &v12);
  v16 = &v14;
  v14 = 0;
  if ( v9 )
    v10 = v9 + *(int *)(*(_QWORD *)(v9 + 8) + 4LL) + 8LL;
  else
    v10 = 0;
  *a2 = v10;
  if ( !v10 )
  {
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, -2147418113);
    throw (ErrorCodeException *)pExceptionObject;
  }
  return a2;
}

```

## disassembly

```asm
0x180026404  mov     [rsp-28h+arg_8], rdx
0x180026409  push    rbp
0x18002640a  push    rbx
0x18002640b  push    rsi
0x18002640c  push    rdi
0x18002640d  push    r14
0x18002640f  mov     rbp, rsp
0x180026412  sub     rsp, 70h
0x180026416  mov     r14, r8
0x180026419  mov     rbx, rdx
0x18002641c  mov     rdi, rcx
0x18002641f  mov     ecx, 50h ; 'P'; Size
0x180026424  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026429  mov     rsi, rax
0x18002642c  mov     [rbp+arg_18], rax
0x180026430  lea     rax, [rbp+var_38]
0x180026434  mov     [rbp+var_48], rax
0x180026438  xorps   xmm0, xmm0
0x18002643b  movdqu  [rbp+var_38], xmm0
0x180026440  mov     rcx, [rdi-18h]
0x180026444  test    rcx, rcx
0x180026447  jz      short loc_18002644D
0x180026449  lock inc dword ptr [rcx+8]
0x18002644d  mov     rax, [rdi-20h]
0x180026451  mov     qword ptr [rbp+var_38], rax
0x180026455  mov     rax, [rdi-18h]
0x180026459  mov     qword ptr [rbp+var_38+8], rax
0x18002645d  mov     rdx, r14
0x180026460  lea     rcx, [rbp+pExceptionObject]
0x180026464  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180026469  nop
0x18002646a  lea     r8, [rbp+var_38]
0x18002646e  mov     rdx, rax
0x180026471  mov     rcx, rsi
0x180026474  call    _anonymous_namespace___StorageValue_256___StorageValue_256_
0x180026479  mov     rdx, rax
0x18002647c  lea     rax, [rbp+arg_0]
0x180026480  mov     [rbp+arg_18], rax
0x180026484  mov     [rbp+arg_0], 0
0x18002648c  test    rdx, rdx
0x18002648f  jnz     short loc_180026495
0x180026491  xor     eax, eax
0x180026493  jmp     short loc_1800264A4
0x180026495  mov     rax, [rdx+8]
0x180026499  movsxd  rax, dword ptr [rax+4]
0x18002649d  add     rax, 8
0x1800264a1  add     rax, rdx
0x1800264a4  mov     [rbx], rax
0x1800264a7  test    rax, rax
0x1800264aa  jz      short loc_1800264BA
0x1800264ac  mov     rax, rbx
0x1800264af  add     rsp, 70h
0x1800264b3  pop     r14
0x1800264b5  pop     rdi
0x1800264b6  pop     rsi
0x1800264b7  pop     rbx
0x1800264b8  pop     rbp
0x1800264b9  retn
0x1800264ba  mov     edx, 8000FFFFh; int
0x1800264bf  lea     rcx, [rbp+pExceptionObject]; this
0x1800264c3  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x1800264c8  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x1800264cf  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800264d3  call    _CxxThrowException_0
```
