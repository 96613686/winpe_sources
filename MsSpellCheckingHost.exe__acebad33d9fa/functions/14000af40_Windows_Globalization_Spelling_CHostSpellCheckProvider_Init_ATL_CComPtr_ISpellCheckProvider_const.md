# Windows::Globalization::Spelling::CHostSpellCheckProvider::Init(ATL::CComPtr<ISpellCheckProvider> const &)

- ea: `0x14000af40`
- end: `0x14000afaf`
- name: `?Init@CHostSpellCheckProvider@Spelling@Globalization@Windows@@UEAAJAEBV?$CComPtr@UISpellCheckProvider@@@ATL@@@Z`
- size: `111`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000af40`
- `0x140013010`

## pseudocode

```c
__int64 __fastcall Windows::Globalization::Spelling::CHostSpellCheckProvider::Init(__int64 a1, _QWORD *a2)
{
  __int64 v2; // rbx
  __int64 v4; // rcx

  v2 = *a2;
  if ( *(_QWORD *)(a1 + 48) == *a2 )
  {
    v2 = *(_QWORD *)(a1 + 48);
  }
  else
  {
    if ( v2 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v2 + 8LL))(*a2);
    v4 = *(_QWORD *)(a1 + 48);
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    *(_QWORD *)(a1 + 48) = v2;
  }
  (**(void (__fastcall ***)(__int64, GUID *, __int64))v2)(v2, &GUID_0c58f8de_8e94_479e_9717_70c42c4ad2c3, a1 + 56);
  return 0;
}

```

## disassembly

```asm
0x14000af40  mov     [rsp+arg_0], rbx
0x14000af45  push    rdi
0x14000af46  sub     rsp, 20h
0x14000af4a  mov     rbx, [rdx]
0x14000af4d  mov     rdi, rcx
0x14000af50  cmp     [rcx+30h], rbx
0x14000af54  jz      short loc_14000AF85
0x14000af56  test    rbx, rbx
0x14000af59  jz      short loc_14000AF6A
0x14000af5b  mov     rax, [rbx]
0x14000af5e  mov     rcx, rbx
0x14000af61  mov     rax, [rax+8]
0x14000af65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000af6a  mov     rcx, [rdi+30h]
0x14000af6e  test    rcx, rcx
0x14000af71  jz      short loc_14000AF7F
0x14000af73  mov     rax, [rcx]
0x14000af76  mov     rax, [rax+10h]
0x14000af7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000af7f  mov     [rdi+30h], rbx
0x14000af83  jmp     short loc_14000AF89
0x14000af85  mov     rbx, [rcx+30h]
0x14000af89  mov     rax, [rbx]
0x14000af8c  lea     r8, [rdi+38h]
0x14000af90  lea     rdx, _GUID_0c58f8de_8e94_479e_9717_70c42c4ad2c3
0x14000af97  mov     rcx, rbx
0x14000af9a  mov     rax, [rax]
0x14000af9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000afa2  mov     rbx, [rsp+28h+arg_0]
0x14000afa7  xor     eax, eax
0x14000afa9  add     rsp, 20h
0x14000afad  pop     rdi
0x14000afae  retn
```
