# ConfigSystemContext::IsWritableConfigSystem(void)

- ea: `0x18000dc48`
- end: `0x18000dca7`
- name: `?IsWritableConfigSystem@ConfigSystemContext@@QEAA_NXZ`
- size: `95`
- prototype: `bool __fastcall(ConfigSystemContext *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b8ec`
- `0x18000bc0c`

## callees

- `0x1800021a4`
- `0x18000dc48`
- `0x180012f3c`
- `0x180014010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall ConfigSystemContext::IsWritableConfigSystem(ConfigSystemContext *this)
{
  char v1; // bl
  int v2; // eax
  int pExceptionObject; // [rsp+30h] [rbp+8h] BYREF
  __int64 v5; // [rsp+38h] [rbp+10h] BYREF

  v1 = 0;
  v5 = 0;
  v2 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 2))(
         *((_QWORD *)this + 2),
         &GUID_fa7660f6_7b3f_4237_a8bf_ed0ad0dcbbd9,
         &v5);
  if ( v2 < 0 )
  {
    if ( v2 != -2147467262 )
    {
      pExceptionObject = v2;
      throw (long *)&pExceptionObject;
    }
  }
  else
  {
    v1 = 1;
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v5);
  return v1;
}

```

## disassembly

```asm
0x18000dc48  push    rbx
0x18000dc4a  sub     rsp, 20h
0x18000dc4e  xor     ebx, ebx
0x18000dc50  mov     [rsp+28h+arg_8], rbx
0x18000dc55  mov     rcx, [rcx+10h]
0x18000dc59  mov     rax, [rcx]
0x18000dc5c  lea     r8, [rsp+28h+arg_8]
0x18000dc61  lea     rdx, _GUID_fa7660f6_7b3f_4237_a8bf_ed0ad0dcbbd9
0x18000dc68  mov     rax, [rax]
0x18000dc6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc70  test    eax, eax
0x18000dc72  js      short loc_18000DC78
0x18000dc74  mov     bl, 1
0x18000dc76  jmp     short loc_18000DC7F
0x18000dc78  cmp     eax, 80004002h
0x18000dc7d  jnz     short loc_18000DC91
0x18000dc7f  lea     rcx, [rsp+28h+arg_8]
0x18000dc84  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000dc89  mov     al, bl
0x18000dc8b  add     rsp, 20h
0x18000dc8f  pop     rbx
0x18000dc90  retn
0x18000dc91  mov     [rsp+28h+pExceptionObject], eax
0x18000dc95  lea     rdx, _TI1J; pThrowInfo
0x18000dc9c  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18000dca1  call    _CxxThrowException_0
```
