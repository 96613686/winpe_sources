# __DllMainCRTStartup

- ea: `0x180006e94`
- end: `0x1800070a0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180006e50`

## callees

- `0x18000557c`
- `0x180006c20`
- `0x180006e94`
- `0x18000767d`
- `0x18000b6a0`

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
  if ( (_DWORD)fdwReason || dword_1800122A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800122A4 = 1;
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
            if ( dword_1800122A4 )
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
0x180006e94  mov     [rsp+lpvReserved], r8
0x180006e99  mov     [rsp+arg_8], edx
0x180006e9d  mov     [rsp+arg_0], rcx
0x180006ea2  push    rbx
0x180006ea3  push    rsi
0x180006ea4  push    rdi
0x180006ea5  sub     rsp, 0F0h
0x180006eac  mov     edi, edx
0x180006eae  mov     rsi, rcx
0x180006eb1  mov     ebx, 1
0x180006eb6  cmp     edx, ebx
0x180006eb8  ja      short loc_180006EC0
0x180006eba  mov     cs:__native_dllmain_reason, edx
0x180006ec0  test    edx, edx
0x180006ec2  jnz     short loc_180006ED7
0x180006ec4  cmp     cs:dword_1800122A0, edx
0x180006eca  jnz     short loc_180006ED7
0x180006ecc  xor     ebx, ebx
0x180006ece  mov     [rsp+108h+var_E8], ebx
0x180006ed2  jmp     loc_180007084
0x180006ed7  lea     eax, [rdx-1]
0x180006eda  cmp     eax, 1
0x180006edd  ja      loc_180006F64
0x180006ee3  mov     rax, cs:_pRawDllMain
0x180006eea  test    rax, rax
0x180006eed  jz      short loc_180006F25
0x180006eef  cmp     edx, 1
0x180006ef2  jnz     short loc_180006EFA
0x180006ef4  mov     cs:dword_1800122A4, edx
0x180006efa  mov     r8, [rsp+108h+lpvReserved]
0x180006f02  call    cs:__guard_dispatch_icall_fptr
0x180006f08  mov     ebx, eax
0x180006f0a  mov     [rsp+108h+var_E8], eax
0x180006f0e  jmp     short loc_180006F25
0x180006f10  xor     ebx, ebx
0x180006f12  mov     [rsp+108h+var_E8], ebx
0x180006f16  mov     edi, [rsp+108h+arg_8]
0x180006f1d  mov     rsi, [rsp+108h+arg_0]
0x180006f25  test    ebx, ebx
0x180006f27  jz      loc_180007084
0x180006f2d  mov     r8, [rsp+108h+lpvReserved]
0x180006f35  mov     edx, edi
0x180006f37  mov     rcx, rsi
0x180006f3a  call    _CRT_INIT
0x180006f3f  mov     ebx, eax
0x180006f41  mov     [rsp+108h+var_E8], eax
0x180006f45  jmp     short loc_180006F5C
0x180006f47  xor     ebx, ebx
0x180006f49  mov     [rsp+108h+var_E8], ebx
0x180006f4d  mov     edi, [rsp+108h+arg_8]
0x180006f54  mov     rsi, [rsp+108h+arg_0]
0x180006f5c  test    ebx, ebx
0x180006f5e  jz      loc_180007084
0x180006f64  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180006f6c  mov     edx, edi; fdwReason
0x180006f6e  mov     rcx, rsi; hinstDLL
0x180006f71  call    DllMain
0x180006f76  mov     ebx, eax
0x180006f78  mov     [rsp+108h+var_E8], eax
0x180006f7c  jmp     short loc_180006F93
0x180006f7e  xor     ebx, ebx
0x180006f80  mov     [rsp+108h+var_E8], ebx
0x180006f84  mov     edi, [rsp+108h+arg_8]
0x180006f8b  mov     rsi, [rsp+108h+arg_0]
0x180006f93  cmp     edi, 1
0x180006f96  jnz     short loc_18000700F
0x180006f98  test    ebx, ebx
0x180006f9a  jnz     short loc_18000700F
0x180006f9c  xor     r8d, r8d; lpvReserved
0x180006f9f  xor     edx, edx; fdwReason
0x180006fa1  mov     rcx, rsi; hinstDLL
0x180006fa4  call    DllMain
0x180006fa9  jmp     short loc_180006FBE
0x180006fab  mov     edi, [rsp+108h+arg_8]
0x180006fb2  mov     rsi, [rsp+108h+arg_0]
0x180006fba  mov     ebx, [rsp+108h+var_E8]
0x180006fbe  xor     r8d, r8d
0x180006fc1  xor     edx, edx
0x180006fc3  mov     rcx, rsi
0x180006fc6  call    _CRT_INIT
0x180006fcb  jmp     short loc_180006FE0
0x180006fcd  mov     edi, [rsp+108h+arg_8]
0x180006fd4  mov     rsi, [rsp+108h+arg_0]
0x180006fdc  mov     ebx, [rsp+108h+var_E8]
0x180006fe0  mov     rax, cs:_pRawDllMain
0x180006fe7  test    rax, rax
0x180006fea  jz      short loc_18000700F
0x180006fec  xor     r8d, r8d
0x180006fef  xor     edx, edx
0x180006ff1  mov     rcx, rsi
0x180006ff4  call    cs:__guard_dispatch_icall_fptr
0x180006ffa  jmp     short loc_18000700F
0x180006ffc  mov     edi, [rsp+108h+arg_8]
0x180007003  mov     rsi, [rsp+108h+arg_0]
0x18000700b  mov     ebx, [rsp+108h+var_E8]
0x18000700f  test    edi, edi
0x180007011  jz      short loc_180007018
0x180007013  cmp     edi, 3
0x180007016  jnz     short loc_180007084
0x180007018  mov     r8, [rsp+108h+lpvReserved]
0x180007020  mov     edx, edi
0x180007022  mov     rcx, rsi
0x180007025  call    _CRT_INIT
0x18000702a  mov     ebx, eax
0x18000702c  mov     [rsp+108h+var_E8], eax
0x180007030  jmp     short loc_180007047
0x180007032  xor     ebx, ebx
0x180007034  mov     [rsp+108h+var_E8], ebx
0x180007038  mov     edi, [rsp+108h+arg_8]
0x18000703f  mov     rsi, [rsp+108h+arg_0]
0x180007047  mov     rax, cs:_pRawDllMain
0x18000704e  test    rax, rax
0x180007051  jz      short loc_180007084
0x180007053  cmp     cs:dword_1800122A4, 0
0x18000705a  jz      short loc_180007084
0x18000705c  mov     r8, [rsp+108h+lpvReserved]
0x180007064  mov     edx, edi
0x180007066  mov     rcx, rsi
0x180007069  call    cs:__guard_dispatch_icall_fptr
0x18000706f  mov     ebx, eax
0x180007071  mov     [rsp+108h+var_E8], eax
0x180007075  jmp     short loc_180007084
0x180007077  xor     ebx, ebx
0x180007079  mov     [rsp+108h+var_E8], ebx
0x18000707d  mov     edi, [rsp+108h+arg_8]
0x180007084  cmp     edi, 1
0x180007087  ja      short loc_180007093
0x180007089  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180007093  mov     eax, ebx
0x180007095  add     rsp, 0F0h
0x18000709c  pop     rdi
0x18000709d  pop     rsi
0x18000709e  pop     rbx
0x18000709f  retn
0x18000b9e8  push    rbp
0x18000b9ea  sub     rsp, 20h
0x18000b9ee  mov     rbp, rdx
0x18000b9f1  mov     rax, [rcx]
0x18000b9f4  mov     edx, [rax]
0x18000b9f6  mov     [rbp+0A8h], rcx
0x18000b9fd  mov     [rbp+28h], edx
0x18000ba00  mov     eax, [rbp+28h]
0x18000ba03  cmp     eax, 0E06D7363h
0x18000ba08  jnz     short loc_18000BA1E
0x18000ba0a  mov     rdx, [rbp+0A8h]
0x18000ba11  mov     ecx, [rbp+28h]
0x18000ba14  call    _XcptFilter_0
0x18000ba19  mov     [rbp+30h], eax
0x18000ba1c  jmp     short loc_18000BA25
0x18000ba1e  mov     dword ptr [rbp+30h], 0
0x18000ba25  mov     eax, [rbp+30h]
0x18000ba28  add     rsp, 20h
0x18000ba2c  pop     rbp
0x18000ba2d  retn
0x18000ba2f  push    rbp
0x18000ba31  sub     rsp, 20h
0x18000ba35  mov     rbp, rdx
0x18000ba38  mov     rax, [rcx]
0x18000ba3b  mov     edx, [rax]
0x18000ba3d  mov     [rbp+0B0h], rcx
0x18000ba44  mov     [rbp+38h], edx
0x18000ba47  mov     eax, [rbp+38h]
0x18000ba4a  cmp     eax, 0E06D7363h
0x18000ba4f  jnz     short loc_18000BA65
0x18000ba51  mov     rdx, [rbp+0B0h]
0x18000ba58  mov     ecx, [rbp+38h]
0x18000ba5b  call    _XcptFilter_0
0x18000ba60  mov     [rbp+40h], eax
0x18000ba63  jmp     short loc_18000BA6C
0x18000ba65  mov     dword ptr [rbp+40h], 0
0x18000ba6c  mov     eax, [rbp+40h]
0x18000ba6f  add     rsp, 20h
0x18000ba73  pop     rbp
0x18000ba74  retn
0x18000ba76  push    rbp
0x18000ba78  sub     rsp, 20h
0x18000ba7c  mov     rbp, rdx
0x18000ba7f  mov     rax, [rcx]
0x18000ba82  mov     edx, [rax]
0x18000ba84  mov     [rbp+0B8h], rcx
0x18000ba8b  mov     [rbp+48h], edx
0x18000ba8e  mov     eax, [rbp+48h]
0x18000ba91  cmp     eax, 0E06D7363h
0x18000ba96  jnz     short loc_18000BAAC
0x18000ba98  mov     rdx, [rbp+0B8h]
0x18000ba9f  mov     ecx, [rbp+48h]
0x18000baa2  call    _XcptFilter_0
0x18000baa7  mov     [rbp+50h], eax
0x18000baaa  jmp     short loc_18000BAB3
0x18000baac  mov     dword ptr [rbp+50h], 0
0x18000bab3  mov     eax, [rbp+50h]
0x18000bab6  add     rsp, 20h
0x18000baba  pop     rbp
0x18000babb  retn
0x18000babd  push    rbp
0x18000babf  sub     rsp, 20h
0x18000bac3  mov     rbp, rdx
0x18000bac6  mov     rax, [rcx]
0x18000bac9  mov     edx, [rax]
0x18000bacb  mov     [rbp+0C0h], rcx
0x18000bad2  mov     [rbp+58h], edx
0x18000bad5  mov     eax, [rbp+58h]
0x18000bad8  cmp     eax, 0E06D7363h
0x18000badd  jnz     short loc_18000BAF3
0x18000badf  mov     rdx, [rbp+0C0h]
0x18000bae6  mov     ecx, [rbp+58h]
0x18000bae9  call    _XcptFilter_0
0x18000baee  mov     [rbp+60h], eax
0x18000baf1  jmp     short loc_18000BAFA
0x18000baf3  mov     dword ptr [rbp+60h], 0
0x18000bafa  mov     eax, [rbp+60h]
0x18000bafd  add     rsp, 20h
0x18000bb01  pop     rbp
0x18000bb02  retn
0x18000bb04  push    rbp
0x18000bb06  sub     rsp, 20h
0x18000bb0a  mov     rbp, rdx
0x18000bb0d  mov     rax, [rcx]
0x18000bb10  mov     edx, [rax]
0x18000bb12  mov     [rbp+0C8h], rcx
0x18000bb19  mov     [rbp+68h], edx
0x18000bb1c  mov     eax, [rbp+68h]
0x18000bb1f  cmp     eax, 0E06D7363h
0x18000bb24  jnz     short loc_18000BB3A
0x18000bb26  mov     rdx, [rbp+0C8h]
0x18000bb2d  mov     ecx, [rbp+68h]
0x18000bb30  call    _XcptFilter_0
0x18000bb35  mov     [rbp+70h], eax
0x18000bb38  jmp     short loc_18000BB41
0x18000bb3a  mov     dword ptr [rbp+70h], 0
0x18000bb41  mov     eax, [rbp+70h]
0x18000bb44  add     rsp, 20h
0x18000bb48  pop     rbp
0x18000bb49  retn
0x18000bb4b  push    rbp
0x18000bb4d  sub     rsp, 20h
0x18000bb51  mov     rbp, rdx
0x18000bb54  mov     rax, [rcx]
0x18000bb57  mov     edx, [rax]
0x18000bb59  mov     [rbp+0D0h], rcx
0x18000bb60  mov     [rbp+78h], edx
0x18000bb63  mov     eax, [rbp+78h]
0x18000bb66  cmp     eax, 0E06D7363h
0x18000bb6b  jnz     short loc_18000BB84
0x18000bb6d  mov     rdx, [rbp+0D0h]
0x18000bb74  mov     ecx, [rbp+78h]
0x18000bb77  call    _XcptFilter_0
0x18000bb7c  mov     [rbp+80h], eax
0x18000bb82  jmp     short loc_18000BB8E
0x18000bb84  mov     dword ptr [rbp+80h], 0
0x18000bb8e  mov     eax, [rbp+80h]
0x18000bb94  add     rsp, 20h
0x18000bb98  pop     rbp
0x18000bb99  retn
0x18000bb9b  push    rbp
0x18000bb9d  sub     rsp, 20h
0x18000bba1  mov     rbp, rdx
0x18000bba4  mov     rax, [rcx]
0x18000bba7  mov     edx, [rax]
0x18000bba9  mov     [rbp+0D8h], rcx
0x18000bbb0  mov     [rbp+88h], edx
0x18000bbb6  mov     eax, [rbp+88h]
0x18000bbbc  cmp     eax, 0E06D7363h
0x18000bbc1  jnz     short loc_18000BBDD
0x18000bbc3  mov     rdx, [rbp+0D8h]
0x18000bbca  mov     ecx, [rbp+88h]
0x18000bbd0  call    _XcptFilter_0
0x18000bbd5  mov     [rbp+90h], eax
0x18000bbdb  jmp     short loc_18000BBE7
0x18000bbdd  mov     dword ptr [rbp+90h], 0
0x18000bbe7  mov     eax, [rbp+90h]
0x18000bbed  add     rsp, 20h
0x18000bbf1  pop     rbp
0x18000bbf2  retn
0x18000bbf4  push    rbp
0x18000bbf6  sub     rsp, 20h
0x18000bbfa  mov     rbp, rdx
0x18000bbfd  mov     rax, [rcx]
0x18000bc00  mov     edx, [rax]
0x18000bc02  mov     [rbp+0E0h], rcx
0x18000bc09  mov     [rbp+98h], edx
0x18000bc0f  mov     eax, [rbp+98h]
0x18000bc15  cmp     eax, 0E06D7363h
0x18000bc1a  jnz     short loc_18000BC36
0x18000bc1c  mov     rdx, [rbp+0E0h]
0x18000bc23  mov     ecx, [rbp+98h]
0x18000bc29  call    _XcptFilter_0
0x18000bc2e  mov     [rbp+0A0h], eax
0x18000bc34  jmp     short loc_18000BC40
0x18000bc36  mov     dword ptr [rbp+0A0h], 0
0x18000bc40  mov     eax, [rbp+0A0h]
0x18000bc46  add     rsp, 20h
0x18000bc4a  pop     rbp
0x18000bc4b  retn
0x18000bc4d  push    rbp
0x18000bc4f  sub     rsp, 20h
0x18000bc53  mov     rbp, rdx
0x18000bc56  cmp     dword ptr [rbp+118h], 1
0x18000bc5d  ja      short loc_18000BC69
0x18000bc5f  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
