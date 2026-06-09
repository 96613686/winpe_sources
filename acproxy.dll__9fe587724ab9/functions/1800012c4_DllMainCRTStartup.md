# __DllMainCRTStartup

- ea: `0x1800012c4`
- end: `0x1800014d0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001280`

## callees

- `0x180001050`
- `0x1800012c4`
- `0x1800014d6`
- `0x1800016a8`
- `0x180001c50`

## pseudocode

```c
__int64 __fastcall _DllMainCRTStartup(HINSTANCE hinstDLL, __int64 fdwReason, void *a3)
{
  DWORD v3; // edi
  unsigned int v5; // ebx

  v3 = fdwReason;
  v5 = 1;
  if ( (unsigned int)fdwReason <= 1 )
    _native_dllmain_reason = fdwReason;
  if ( (_DWORD)fdwReason || dword_1800040A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800040A4 = 1;
      v5 = pRawDllMain(hinstDLL, fdwReason, a3);
    }
    if ( v5 )
    {
      v5 = CRT_INIT(hinstDLL, v3, a3);
      if ( v5 )
      {
LABEL_13:
        v5 = DllMain(hinstDLL, v3, a3);
        if ( v3 == 1 && !v5 )
        {
          DllMain(hinstDLL, 0, 0);
          CRT_INIT(hinstDLL, 0, 0);
          if ( pRawDllMain )
            pRawDllMain(hinstDLL, 0, 0);
        }
        if ( !v3 || v3 == 3 )
        {
          v5 = CRT_INIT(hinstDLL, v3, a3);
          if ( pRawDllMain )
          {
            if ( dword_1800040A4 )
              v5 = pRawDllMain(hinstDLL, v3, a3);
          }
        }
      }
    }
  }
  else
  {
    v5 = 0;
  }
  if ( v3 <= 1 )
    _native_dllmain_reason = -1;
  return v5;
}

```

## disassembly

```asm
0x1800012c4  mov     [rsp+lpvReserved], r8
0x1800012c9  mov     [rsp+arg_8], edx
0x1800012cd  mov     [rsp+arg_0], rcx
0x1800012d2  push    rbx
0x1800012d3  push    rsi
0x1800012d4  push    rdi
0x1800012d5  sub     rsp, 0F0h
0x1800012dc  mov     edi, edx
0x1800012de  mov     rsi, rcx
0x1800012e1  mov     ebx, 1
0x1800012e6  cmp     edx, ebx
0x1800012e8  ja      short loc_1800012F0
0x1800012ea  mov     cs:__native_dllmain_reason, edx
0x1800012f0  test    edx, edx
0x1800012f2  jnz     short loc_180001307
0x1800012f4  cmp     cs:dword_1800040A0, edx
0x1800012fa  jnz     short loc_180001307
0x1800012fc  xor     ebx, ebx
0x1800012fe  mov     [rsp+108h+var_E8], ebx
0x180001302  jmp     loc_1800014B4
0x180001307  lea     eax, [rdx-1]
0x18000130a  cmp     eax, 1
0x18000130d  ja      loc_180001394
0x180001313  mov     rax, cs:_pRawDllMain
0x18000131a  test    rax, rax
0x18000131d  jz      short loc_180001355
0x18000131f  cmp     edx, 1
0x180001322  jnz     short loc_18000132A
0x180001324  mov     cs:dword_1800040A4, edx
0x18000132a  mov     r8, [rsp+108h+lpvReserved]
0x180001332  call    cs:__guard_dispatch_icall_fptr
0x180001338  mov     ebx, eax
0x18000133a  mov     [rsp+108h+var_E8], eax
0x18000133e  jmp     short loc_180001355
0x180001340  xor     ebx, ebx
0x180001342  mov     [rsp+108h+var_E8], ebx
0x180001346  mov     edi, [rsp+108h+arg_8]
0x18000134d  mov     rsi, [rsp+108h+arg_0]
0x180001355  test    ebx, ebx
0x180001357  jz      loc_1800014B4
0x18000135d  mov     r8, [rsp+108h+lpvReserved]
0x180001365  mov     edx, edi
0x180001367  mov     rcx, rsi
0x18000136a  call    _CRT_INIT
0x18000136f  mov     ebx, eax
0x180001371  mov     [rsp+108h+var_E8], eax
0x180001375  jmp     short loc_18000138C
0x180001377  xor     ebx, ebx
0x180001379  mov     [rsp+108h+var_E8], ebx
0x18000137d  mov     edi, [rsp+108h+arg_8]
0x180001384  mov     rsi, [rsp+108h+arg_0]
0x18000138c  test    ebx, ebx
0x18000138e  jz      loc_1800014B4
0x180001394  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000139c  mov     edx, edi; fdwReason
0x18000139e  mov     rcx, rsi; hinstDLL
0x1800013a1  call    DllMain
0x1800013a6  mov     ebx, eax
0x1800013a8  mov     [rsp+108h+var_E8], eax
0x1800013ac  jmp     short loc_1800013C3
0x1800013ae  xor     ebx, ebx
0x1800013b0  mov     [rsp+108h+var_E8], ebx
0x1800013b4  mov     edi, [rsp+108h+arg_8]
0x1800013bb  mov     rsi, [rsp+108h+arg_0]
0x1800013c3  cmp     edi, 1
0x1800013c6  jnz     short loc_18000143F
0x1800013c8  test    ebx, ebx
0x1800013ca  jnz     short loc_18000143F
0x1800013cc  xor     r8d, r8d; lpvReserved
0x1800013cf  xor     edx, edx; fdwReason
0x1800013d1  mov     rcx, rsi; hinstDLL
0x1800013d4  call    DllMain
0x1800013d9  jmp     short loc_1800013EE
0x1800013db  mov     edi, [rsp+108h+arg_8]
0x1800013e2  mov     rsi, [rsp+108h+arg_0]
0x1800013ea  mov     ebx, [rsp+108h+var_E8]
0x1800013ee  xor     r8d, r8d
0x1800013f1  xor     edx, edx
0x1800013f3  mov     rcx, rsi
0x1800013f6  call    _CRT_INIT
0x1800013fb  jmp     short loc_180001410
0x1800013fd  mov     edi, [rsp+108h+arg_8]
0x180001404  mov     rsi, [rsp+108h+arg_0]
0x18000140c  mov     ebx, [rsp+108h+var_E8]
0x180001410  mov     rax, cs:_pRawDllMain
0x180001417  test    rax, rax
0x18000141a  jz      short loc_18000143F
0x18000141c  xor     r8d, r8d
0x18000141f  xor     edx, edx
0x180001421  mov     rcx, rsi
0x180001424  call    cs:__guard_dispatch_icall_fptr
0x18000142a  jmp     short loc_18000143F
0x18000142c  mov     edi, [rsp+108h+arg_8]
0x180001433  mov     rsi, [rsp+108h+arg_0]
0x18000143b  mov     ebx, [rsp+108h+var_E8]
0x18000143f  test    edi, edi
0x180001441  jz      short loc_180001448
0x180001443  cmp     edi, 3
0x180001446  jnz     short loc_1800014B4
0x180001448  mov     r8, [rsp+108h+lpvReserved]
0x180001450  mov     edx, edi
0x180001452  mov     rcx, rsi
0x180001455  call    _CRT_INIT
0x18000145a  mov     ebx, eax
0x18000145c  mov     [rsp+108h+var_E8], eax
0x180001460  jmp     short loc_180001477
0x180001462  xor     ebx, ebx
0x180001464  mov     [rsp+108h+var_E8], ebx
0x180001468  mov     edi, [rsp+108h+arg_8]
0x18000146f  mov     rsi, [rsp+108h+arg_0]
0x180001477  mov     rax, cs:_pRawDllMain
0x18000147e  test    rax, rax
0x180001481  jz      short loc_1800014B4
0x180001483  cmp     cs:dword_1800040A4, 0
0x18000148a  jz      short loc_1800014B4
0x18000148c  mov     r8, [rsp+108h+lpvReserved]
0x180001494  mov     edx, edi
0x180001496  mov     rcx, rsi
0x180001499  call    cs:__guard_dispatch_icall_fptr
0x18000149f  mov     ebx, eax
0x1800014a1  mov     [rsp+108h+var_E8], eax
0x1800014a5  jmp     short loc_1800014B4
0x1800014a7  xor     ebx, ebx
0x1800014a9  mov     [rsp+108h+var_E8], ebx
0x1800014ad  mov     edi, [rsp+108h+arg_8]
0x1800014b4  cmp     edi, 1
0x1800014b7  ja      short loc_1800014C3
0x1800014b9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800014c3  mov     eax, ebx
0x1800014c5  add     rsp, 0F0h
0x1800014cc  pop     rdi
0x1800014cd  pop     rsi
0x1800014ce  pop     rbx
0x1800014cf  retn
0x180001c90  push    rbp
0x180001c92  sub     rsp, 20h
0x180001c96  mov     rbp, rdx
0x180001c99  mov     rax, [rcx]
0x180001c9c  mov     edx, [rax]
0x180001c9e  mov     [rbp+0A8h], rcx
0x180001ca5  mov     [rbp+28h], edx
0x180001ca8  mov     eax, [rbp+28h]
0x180001cab  cmp     eax, 0E06D7363h
0x180001cb0  jnz     short loc_180001CC6
0x180001cb2  mov     rdx, [rbp+0A8h]
0x180001cb9  mov     ecx, [rbp+28h]
0x180001cbc  call    _XcptFilter_0
0x180001cc1  mov     [rbp+30h], eax
0x180001cc4  jmp     short loc_180001CCD
0x180001cc6  mov     dword ptr [rbp+30h], 0
0x180001ccd  mov     eax, [rbp+30h]
0x180001cd0  add     rsp, 20h
0x180001cd4  pop     rbp
0x180001cd5  retn
0x180001cd7  push    rbp
0x180001cd9  sub     rsp, 20h
0x180001cdd  mov     rbp, rdx
0x180001ce0  mov     rax, [rcx]
0x180001ce3  mov     edx, [rax]
0x180001ce5  mov     [rbp+0B0h], rcx
0x180001cec  mov     [rbp+38h], edx
0x180001cef  mov     eax, [rbp+38h]
0x180001cf2  cmp     eax, 0E06D7363h
0x180001cf7  jnz     short loc_180001D0D
0x180001cf9  mov     rdx, [rbp+0B0h]
0x180001d00  mov     ecx, [rbp+38h]
0x180001d03  call    _XcptFilter_0
0x180001d08  mov     [rbp+40h], eax
0x180001d0b  jmp     short loc_180001D14
0x180001d0d  mov     dword ptr [rbp+40h], 0
0x180001d14  mov     eax, [rbp+40h]
0x180001d17  add     rsp, 20h
0x180001d1b  pop     rbp
0x180001d1c  retn
0x180001d1e  push    rbp
0x180001d20  sub     rsp, 20h
0x180001d24  mov     rbp, rdx
0x180001d27  mov     rax, [rcx]
0x180001d2a  mov     edx, [rax]
0x180001d2c  mov     [rbp+0B8h], rcx
0x180001d33  mov     [rbp+48h], edx
0x180001d36  mov     eax, [rbp+48h]
0x180001d39  cmp     eax, 0E06D7363h
0x180001d3e  jnz     short loc_180001D54
0x180001d40  mov     rdx, [rbp+0B8h]
0x180001d47  mov     ecx, [rbp+48h]
0x180001d4a  call    _XcptFilter_0
0x180001d4f  mov     [rbp+50h], eax
0x180001d52  jmp     short loc_180001D5B
0x180001d54  mov     dword ptr [rbp+50h], 0
0x180001d5b  mov     eax, [rbp+50h]
0x180001d5e  add     rsp, 20h
0x180001d62  pop     rbp
0x180001d63  retn
0x180001d65  push    rbp
0x180001d67  sub     rsp, 20h
0x180001d6b  mov     rbp, rdx
0x180001d6e  mov     rax, [rcx]
0x180001d71  mov     edx, [rax]
0x180001d73  mov     [rbp+0C0h], rcx
0x180001d7a  mov     [rbp+58h], edx
0x180001d7d  mov     eax, [rbp+58h]
0x180001d80  cmp     eax, 0E06D7363h
0x180001d85  jnz     short loc_180001D9B
0x180001d87  mov     rdx, [rbp+0C0h]
0x180001d8e  mov     ecx, [rbp+58h]
0x180001d91  call    _XcptFilter_0
0x180001d96  mov     [rbp+60h], eax
0x180001d99  jmp     short loc_180001DA2
0x180001d9b  mov     dword ptr [rbp+60h], 0
0x180001da2  mov     eax, [rbp+60h]
0x180001da5  add     rsp, 20h
0x180001da9  pop     rbp
0x180001daa  retn
0x180001dac  push    rbp
0x180001dae  sub     rsp, 20h
0x180001db2  mov     rbp, rdx
0x180001db5  mov     rax, [rcx]
0x180001db8  mov     edx, [rax]
0x180001dba  mov     [rbp+0C8h], rcx
0x180001dc1  mov     [rbp+68h], edx
0x180001dc4  mov     eax, [rbp+68h]
0x180001dc7  cmp     eax, 0E06D7363h
0x180001dcc  jnz     short loc_180001DE2
0x180001dce  mov     rdx, [rbp+0C8h]
0x180001dd5  mov     ecx, [rbp+68h]
0x180001dd8  call    _XcptFilter_0
0x180001ddd  mov     [rbp+70h], eax
0x180001de0  jmp     short loc_180001DE9
0x180001de2  mov     dword ptr [rbp+70h], 0
0x180001de9  mov     eax, [rbp+70h]
0x180001dec  add     rsp, 20h
0x180001df0  pop     rbp
0x180001df1  retn
0x180001df3  push    rbp
0x180001df5  sub     rsp, 20h
0x180001df9  mov     rbp, rdx
0x180001dfc  mov     rax, [rcx]
0x180001dff  mov     edx, [rax]
0x180001e01  mov     [rbp+0D0h], rcx
0x180001e08  mov     [rbp+78h], edx
0x180001e0b  mov     eax, [rbp+78h]
0x180001e0e  cmp     eax, 0E06D7363h
0x180001e13  jnz     short loc_180001E2C
0x180001e15  mov     rdx, [rbp+0D0h]
0x180001e1c  mov     ecx, [rbp+78h]
0x180001e1f  call    _XcptFilter_0
0x180001e24  mov     [rbp+80h], eax
0x180001e2a  jmp     short loc_180001E36
0x180001e2c  mov     dword ptr [rbp+80h], 0
0x180001e36  mov     eax, [rbp+80h]
0x180001e3c  add     rsp, 20h
0x180001e40  pop     rbp
0x180001e41  retn
0x180001e43  push    rbp
0x180001e45  sub     rsp, 20h
0x180001e49  mov     rbp, rdx
0x180001e4c  mov     rax, [rcx]
0x180001e4f  mov     edx, [rax]
0x180001e51  mov     [rbp+0D8h], rcx
0x180001e58  mov     [rbp+88h], edx
0x180001e5e  mov     eax, [rbp+88h]
0x180001e64  cmp     eax, 0E06D7363h
0x180001e69  jnz     short loc_180001E85
0x180001e6b  mov     rdx, [rbp+0D8h]
0x180001e72  mov     ecx, [rbp+88h]
0x180001e78  call    _XcptFilter_0
0x180001e7d  mov     [rbp+90h], eax
0x180001e83  jmp     short loc_180001E8F
0x180001e85  mov     dword ptr [rbp+90h], 0
0x180001e8f  mov     eax, [rbp+90h]
0x180001e95  add     rsp, 20h
0x180001e99  pop     rbp
0x180001e9a  retn
0x180001e9c  push    rbp
0x180001e9e  sub     rsp, 20h
0x180001ea2  mov     rbp, rdx
0x180001ea5  mov     rax, [rcx]
0x180001ea8  mov     edx, [rax]
0x180001eaa  mov     [rbp+0E0h], rcx
0x180001eb1  mov     [rbp+98h], edx
0x180001eb7  mov     eax, [rbp+98h]
0x180001ebd  cmp     eax, 0E06D7363h
0x180001ec2  jnz     short loc_180001EDE
0x180001ec4  mov     rdx, [rbp+0E0h]
0x180001ecb  mov     ecx, [rbp+98h]
0x180001ed1  call    _XcptFilter_0
0x180001ed6  mov     [rbp+0A0h], eax
0x180001edc  jmp     short loc_180001EE8
0x180001ede  mov     dword ptr [rbp+0A0h], 0
0x180001ee8  mov     eax, [rbp+0A0h]
0x180001eee  add     rsp, 20h
0x180001ef2  pop     rbp
0x180001ef3  retn
0x180001ef5  push    rbp
0x180001ef7  sub     rsp, 20h
0x180001efb  mov     rbp, rdx
0x180001efe  cmp     dword ptr [rbp+118h], 1
0x180001f05  ja      short loc_180001F11
0x180001f07  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
