# CodeIntegrity::Management::AuthorizationToken::~AuthorizationToken(void)

- ea: `0x180005494`
- end: `0x1800054e6`
- name: `??1AuthorizationToken@Management@CodeIntegrity@@QEAA@XZ`
- size: `82`
- prototype: `void __fastcall(void **this)`
- caller_count: `11`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800057d8`
- `0x180010e30`
- `0x180010e60`
- `0x180011f20`
- `0x180013660`
- `0x180018774`
- `0x180018834`
- `0x18001c714`
- `0x18002a7b3`
- `0x18002adbc`
- `0x18002b607`

## callees

- `0x1800052e4`
- `0x180005308`
- `0x18000558c`
- `0x180008390`
- `0x1800083d4`
- `0x180008430`

## pseudocode

```c
void __fastcall CodeIntegrity::Management::AuthorizationToken::~AuthorizationToken(void **this)
{
  std::unique_ptr<_GUID>::~unique_ptr<_GUID>(this + 27);
  std::unique_ptr<std::array<unsigned char,32>>::~unique_ptr<std::array<unsigned char,32>>(this + 26);
  std::vector<std::array<unsigned char,64>>::_Tidy(this + 23);
  std::vector<std::array<unsigned char,48>>::_Tidy(this + 20);
  std::vector<std::array<unsigned char,32>>::_Tidy(this + 17);
  CodeIntegrity::Management::detail::SbcpTokenView::~SbcpTokenView((CodeIntegrity::Management::detail::SbcpTokenView *)this);
}

```

## disassembly

```asm
0x180005494  push    rbx
0x180005496  sub     rsp, 20h
0x18000549a  mov     rbx, rcx
0x18000549d  add     rcx, 0D8h
0x1800054a4  call    ??1?$unique_ptr@U_GUID@@U?$default_delete@U_GUID@@@std@@@std@@QEAA@XZ; std::unique_ptr<_GUID>::~unique_ptr<_GUID>(void)
0x1800054a9  lea     rcx, [rbx+0D0h]
0x1800054b0  call    ??1?$unique_ptr@V?$array@E$0CA@@std@@U?$default_delete@V?$array@E$0CA@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::array<uchar,32>>::~unique_ptr<std::array<uchar,32>>(void)
0x1800054b5  lea     rcx, [rbx+0B8h]
0x1800054bc  call    ?_Tidy@?$vector@V?$array@E$0EA@@std@@V?$allocator@V?$array@E$0EA@@std@@@2@@std@@AEAAXXZ; std::vector<std::array<uchar,64>>::_Tidy(void)
0x1800054c1  lea     rcx, [rbx+0A0h]
0x1800054c8  call    ?_Tidy@?$vector@V?$array@E$0DA@@std@@V?$allocator@V?$array@E$0DA@@std@@@2@@std@@AEAAXXZ; std::vector<std::array<uchar,48>>::_Tidy(void)
0x1800054cd  lea     rcx, [rbx+88h]
0x1800054d4  call    ?_Tidy@?$vector@V?$array@E$0CA@@std@@V?$allocator@V?$array@E$0CA@@std@@@2@@std@@AEAAXXZ; std::vector<std::array<uchar,32>>::_Tidy(void)
0x1800054d9  mov     rcx, rbx; this
0x1800054dc  add     rsp, 20h
0x1800054e0  pop     rbx
0x1800054e1  jmp     ??1SbcpTokenView@detail@Management@CodeIntegrity@@IEAA@XZ; CodeIntegrity::Management::detail::SbcpTokenView::~SbcpTokenView(void)
```
