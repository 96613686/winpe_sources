# DllGetClassObject

- ea: `0x180016920`
- end: `0x180016981`
- name: `DllGetClassObject`
- size: `97`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180016920`
- `0x18001e010`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  unsigned __int64 i; // r9
  _QWORD *v5; // rdx
  __int64 v6; // rax

  for ( i = 0; i < 5; ++i )
  {
    v5 = *(&g_aclscache + 2 * i);
    v6 = *(_QWORD *)&rclsid->Data1 - *v5;
    if ( *(_QWORD *)&rclsid->Data1 == *v5 )
      v6 = *(_QWORD *)rclsid->Data4 - v5[1];
    if ( !v6 )
    {
      _mm_lfence();
      return (**(__int64 (__fastcall ***)(_QWORD, const IID *const, LPVOID *))*(&g_aclscache + 2 * i + 1))(
               *(&g_aclscache + 2 * i + 1),
               riid,
               ppv);
    }
  }
  *ppv = 0;
  return -2147221231;
}

```

## disassembly

```asm
0x180016920  push    rbx
0x180016922  mov     r11, rdx
0x180016925  lea     rbx, ?g_aclscache@@3PAUCLSCACHE@@A; CLSCACHE near * g_aclscache
0x18001692c  mov     r10, rcx
0x18001692f  xor     r9d, r9d
0x180016932  cmp     r9, 5
0x180016936  jnb     short loc_180016973
0x180016938  mov     rax, [r10]
0x18001693b  mov     rcx, r9
0x18001693e  add     rcx, rcx
0x180016941  mov     rdx, [rbx+rcx*8]
0x180016945  sub     rax, [rdx]
0x180016948  jnz     short loc_180016952
0x18001694a  mov     rax, [r10+8]
0x18001694e  sub     rax, [rdx+8]
0x180016952  test    rax, rax
0x180016955  jz      short loc_18001695C
0x180016957  inc     r9
0x18001695a  jmp     short loc_180016932
0x18001695c  lfence
0x18001695f  mov     rcx, [rbx+rcx*8+8]
0x180016964  mov     rdx, r11
0x180016967  mov     rax, [rcx]
0x18001696a  mov     rax, [rax]
0x18001696d  pop     rbx
0x18001696e  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180016973  mov     qword ptr [r8], 0
0x18001697a  mov     eax, 80040111h
0x18001697f  pop     rbx
0x180016980  retn
```
