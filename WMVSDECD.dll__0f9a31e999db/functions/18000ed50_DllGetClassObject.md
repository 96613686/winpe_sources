# DllGetClassObject

- ea: `0x18000ed50`
- end: `0x18000ee40`
- name: `DllGetClassObject`
- size: `240`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800010cc`
- `0x18000e720`
- `0x18000ed50`
- `0x18003b010`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  __int64 v6; // rax
  __int64 v7; // rax
  int i; // ecx
  char *v9; // rdi
  __int64 v10; // rax
  __int64 v11; // rax
  void *v12; // rax

  if ( !ppv )
    return -2147467261;
  *ppv = 0;
  v6 = *(_QWORD *)&riid->Data1;
  if ( !*(_QWORD *)&riid->Data1 )
    v6 = *(_QWORD *)riid->Data4 - 0x46000000000000C0LL;
  if ( !v6 )
    goto LABEL_10;
  v7 = *(_QWORD *)&riid->Data1 - 1LL;
  if ( *(_QWORD *)&riid->Data1 == 1 )
    v7 = *(_QWORD *)riid->Data4 - 0x46000000000000C0LL;
  if ( v7 )
    return -2147467262;
LABEL_10:
  for ( i = 0; ; ++i )
  {
    if ( i >= 1 )
      return -2147221231;
    v9 = (char *)&off_180042000 + 16 * i;
    v10 = **(_QWORD **)v9 - *(_QWORD *)&rclsid->Data1;
    if ( !v10 )
      v10 = *(_QWORD *)(*(_QWORD *)v9 + 8LL) - *(_QWORD *)rclsid->Data4;
    if ( !v10 )
      break;
  }
  v11 = sub_1800010CC(24);
  if ( v11 )
  {
    v12 = (void *)sub_18000E720(v11, v9);
    *ppv = v12;
    if ( v12 )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)v12 + 8LL))(v12);
      return 0;
    }
  }
  else
  {
    *ppv = 0;
  }
  return -2147024882;
}

```

## disassembly

```asm
0x18000ed50  mov     [rsp+arg_0], rbx
0x18000ed55  push    rdi
0x18000ed56  sub     rsp, 20h
0x18000ed5a  mov     rbx, r8
0x18000ed5d  mov     r8, rcx
0x18000ed60  test    rbx, rbx
0x18000ed63  jnz     short loc_18000ED6F
0x18000ed65  mov     eax, 80004003h
0x18000ed6a  jmp     loc_18000EE34
0x18000ed6f  mov     qword ptr [rbx], 0
0x18000ed76  mov     rax, [rdx]
0x18000ed79  sub     rax, cs:qword_18003DBF8
0x18000ed80  jnz     short loc_18000ED8D
0x18000ed82  mov     rax, [rdx+8]
0x18000ed86  sub     rax, cs:qword_18003DC00
0x18000ed8d  test    rax, rax
0x18000ed90  jz      short loc_18000EDB5
0x18000ed92  mov     rax, [rdx]
0x18000ed95  sub     rax, cs:qword_18003DC08
0x18000ed9c  jnz     short loc_18000EDA9
0x18000ed9e  mov     rax, [rdx+8]
0x18000eda2  sub     rax, cs:qword_18003DC10
0x18000eda9  test    rax, rax
0x18000edac  jz      short loc_18000EDB5
0x18000edae  mov     eax, 80004002h
0x18000edb3  jmp     short loc_18000EE34
0x18000edb5  xor     ecx, ecx
0x18000edb7  cmp     ecx, 1
0x18000edba  jge     short loc_18000EE2F
0x18000edbc  lea     rdx, off_180042000
0x18000edc3  movsxd  rdi, ecx
0x18000edc6  shl     rdi, 4
0x18000edca  add     rdi, rdx
0x18000edcd  mov     rdx, [rdi]
0x18000edd0  mov     rax, [rdx]
0x18000edd3  sub     rax, [r8]
0x18000edd6  jnz     short loc_18000EDE0
0x18000edd8  mov     rax, [rdx+8]
0x18000eddc  sub     rax, [r8+8]
0x18000ede0  test    rax, rax
0x18000ede3  jz      short loc_18000EDE9
0x18000ede5  inc     ecx
0x18000ede7  jmp     short loc_18000EDB7
0x18000ede9  mov     ecx, 18h
0x18000edee  call    sub_1800010CC
0x18000edf3  test    rax, rax
0x18000edf6  jz      short loc_18000EE21
0x18000edf8  mov     rdx, rdi
0x18000edfb  mov     rcx, rax
0x18000edfe  call    sub_18000E720
0x18000ee03  mov     [rbx], rax
0x18000ee06  mov     rdx, rax
0x18000ee09  test    rax, rax
0x18000ee0c  jz      short loc_18000EE28
0x18000ee0e  mov     rcx, [rax]
0x18000ee11  mov     rax, [rcx+8]
0x18000ee15  mov     rcx, rdx
0x18000ee18  call    j__guard_dispatch_icall
0x18000ee1d  xor     eax, eax
0x18000ee1f  jmp     short loc_18000EE34
0x18000ee21  mov     qword ptr [rbx], 0
0x18000ee28  mov     eax, 8007000Eh
0x18000ee2d  jmp     short loc_18000EE34
0x18000ee2f  mov     eax, 80040111h
0x18000ee34  mov     rbx, [rsp+28h+arg_0]
0x18000ee39  add     rsp, 20h
0x18000ee3d  pop     rdi
0x18000ee3e  retn
```
