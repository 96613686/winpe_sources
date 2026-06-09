# __DllMainCRTStartup

- ea: `0x180001314`
- end: `0x180001520`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800012d0`

## callees

- `0x1800010a0`
- `0x180001314`
- `0x18000154a`
- `0x180003ec8`
- `0x180005200`

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
  if ( (_DWORD)fdwReason || dword_18000B000 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18000B004 = 1;
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
            if ( dword_18000B004 )
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
0x180001314  mov     [rsp+lpvReserved], r8
0x180001319  mov     [rsp+arg_8], edx
0x18000131d  mov     [rsp+arg_0], rcx
0x180001322  push    rbx
0x180001323  push    rsi
0x180001324  push    rdi
0x180001325  sub     rsp, 0F0h
0x18000132c  mov     edi, edx
0x18000132e  mov     rsi, rcx
0x180001331  mov     ebx, 1
0x180001336  cmp     edx, ebx
0x180001338  ja      short loc_180001340
0x18000133a  mov     cs:__native_dllmain_reason, edx
0x180001340  test    edx, edx
0x180001342  jnz     short loc_180001357
0x180001344  cmp     cs:dword_18000B000, edx
0x18000134a  jnz     short loc_180001357
0x18000134c  xor     ebx, ebx
0x18000134e  mov     [rsp+108h+var_E8], ebx
0x180001352  jmp     loc_180001504
0x180001357  lea     eax, [rdx-1]
0x18000135a  cmp     eax, 1
0x18000135d  ja      loc_1800013E4
0x180001363  mov     rax, cs:_pRawDllMain
0x18000136a  test    rax, rax
0x18000136d  jz      short loc_1800013A5
0x18000136f  cmp     edx, 1
0x180001372  jnz     short loc_18000137A
0x180001374  mov     cs:dword_18000B004, edx
0x18000137a  mov     r8, [rsp+108h+lpvReserved]
0x180001382  call    cs:__guard_dispatch_icall_fptr
0x180001388  mov     ebx, eax
0x18000138a  mov     [rsp+108h+var_E8], eax
0x18000138e  jmp     short loc_1800013A5
0x180001390  xor     ebx, ebx
0x180001392  mov     [rsp+108h+var_E8], ebx
0x180001396  mov     edi, [rsp+108h+arg_8]
0x18000139d  mov     rsi, [rsp+108h+arg_0]
0x1800013a5  test    ebx, ebx
0x1800013a7  jz      loc_180001504
0x1800013ad  mov     r8, [rsp+108h+lpvReserved]
0x1800013b5  mov     edx, edi
0x1800013b7  mov     rcx, rsi
0x1800013ba  call    _CRT_INIT
0x1800013bf  mov     ebx, eax
0x1800013c1  mov     [rsp+108h+var_E8], eax
0x1800013c5  jmp     short loc_1800013DC
0x1800013c7  xor     ebx, ebx
0x1800013c9  mov     [rsp+108h+var_E8], ebx
0x1800013cd  mov     edi, [rsp+108h+arg_8]
0x1800013d4  mov     rsi, [rsp+108h+arg_0]
0x1800013dc  test    ebx, ebx
0x1800013de  jz      loc_180001504
0x1800013e4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800013ec  mov     edx, edi; fdwReason
0x1800013ee  mov     rcx, rsi; hinstDLL
0x1800013f1  call    DllMain
0x1800013f6  mov     ebx, eax
0x1800013f8  mov     [rsp+108h+var_E8], eax
0x1800013fc  jmp     short loc_180001413
0x1800013fe  xor     ebx, ebx
0x180001400  mov     [rsp+108h+var_E8], ebx
0x180001404  mov     edi, [rsp+108h+arg_8]
0x18000140b  mov     rsi, [rsp+108h+arg_0]
0x180001413  cmp     edi, 1
0x180001416  jnz     short loc_18000148F
0x180001418  test    ebx, ebx
0x18000141a  jnz     short loc_18000148F
0x18000141c  xor     r8d, r8d; lpvReserved
0x18000141f  xor     edx, edx; fdwReason
0x180001421  mov     rcx, rsi; hinstDLL
0x180001424  call    DllMain
0x180001429  jmp     short loc_18000143E
0x18000142b  mov     edi, [rsp+108h+arg_8]
0x180001432  mov     rsi, [rsp+108h+arg_0]
0x18000143a  mov     ebx, [rsp+108h+var_E8]
0x18000143e  xor     r8d, r8d
0x180001441  xor     edx, edx
0x180001443  mov     rcx, rsi
0x180001446  call    _CRT_INIT
0x18000144b  jmp     short loc_180001460
0x18000144d  mov     edi, [rsp+108h+arg_8]
0x180001454  mov     rsi, [rsp+108h+arg_0]
0x18000145c  mov     ebx, [rsp+108h+var_E8]
0x180001460  mov     rax, cs:_pRawDllMain
0x180001467  test    rax, rax
0x18000146a  jz      short loc_18000148F
0x18000146c  xor     r8d, r8d
0x18000146f  xor     edx, edx
0x180001471  mov     rcx, rsi
0x180001474  call    cs:__guard_dispatch_icall_fptr
0x18000147a  jmp     short loc_18000148F
0x18000147c  mov     edi, [rsp+108h+arg_8]
0x180001483  mov     rsi, [rsp+108h+arg_0]
0x18000148b  mov     ebx, [rsp+108h+var_E8]
0x18000148f  test    edi, edi
0x180001491  jz      short loc_180001498
0x180001493  cmp     edi, 3
0x180001496  jnz     short loc_180001504
0x180001498  mov     r8, [rsp+108h+lpvReserved]
0x1800014a0  mov     edx, edi
0x1800014a2  mov     rcx, rsi
0x1800014a5  call    _CRT_INIT
0x1800014aa  mov     ebx, eax
0x1800014ac  mov     [rsp+108h+var_E8], eax
0x1800014b0  jmp     short loc_1800014C7
0x1800014b2  xor     ebx, ebx
0x1800014b4  mov     [rsp+108h+var_E8], ebx
0x1800014b8  mov     edi, [rsp+108h+arg_8]
0x1800014bf  mov     rsi, [rsp+108h+arg_0]
0x1800014c7  mov     rax, cs:_pRawDllMain
0x1800014ce  test    rax, rax
0x1800014d1  jz      short loc_180001504
0x1800014d3  cmp     cs:dword_18000B004, 0
0x1800014da  jz      short loc_180001504
0x1800014dc  mov     r8, [rsp+108h+lpvReserved]
0x1800014e4  mov     edx, edi
0x1800014e6  mov     rcx, rsi
0x1800014e9  call    cs:__guard_dispatch_icall_fptr
0x1800014ef  mov     ebx, eax
0x1800014f1  mov     [rsp+108h+var_E8], eax
0x1800014f5  jmp     short loc_180001504
0x1800014f7  xor     ebx, ebx
0x1800014f9  mov     [rsp+108h+var_E8], ebx
0x1800014fd  mov     edi, [rsp+108h+arg_8]
0x180001504  cmp     edi, 1
0x180001507  ja      short loc_180001513
0x180001509  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001513  mov     eax, ebx
0x180001515  add     rsp, 0F0h
0x18000151c  pop     rdi
0x18000151d  pop     rsi
0x18000151e  pop     rbx
0x18000151f  retn
0x180005270  push    rbp
0x180005272  sub     rsp, 20h
0x180005276  mov     rbp, rdx
0x180005279  mov     rax, [rcx]
0x18000527c  mov     edx, [rax]
0x18000527e  mov     [rbp+0A8h], rcx
0x180005285  mov     [rbp+28h], edx
0x180005288  mov     eax, [rbp+28h]
0x18000528b  cmp     eax, 0E06D7363h
0x180005290  jnz     short loc_1800052A6
0x180005292  mov     rdx, [rbp+0A8h]
0x180005299  mov     ecx, [rbp+28h]
0x18000529c  call    _XcptFilter_0
0x1800052a1  mov     [rbp+30h], eax
0x1800052a4  jmp     short loc_1800052AD
0x1800052a6  mov     dword ptr [rbp+30h], 0
0x1800052ad  mov     eax, [rbp+30h]
0x1800052b0  add     rsp, 20h
0x1800052b4  pop     rbp
0x1800052b5  retn
0x1800052b7  push    rbp
0x1800052b9  sub     rsp, 20h
0x1800052bd  mov     rbp, rdx
0x1800052c0  mov     rax, [rcx]
0x1800052c3  mov     edx, [rax]
0x1800052c5  mov     [rbp+0B0h], rcx
0x1800052cc  mov     [rbp+38h], edx
0x1800052cf  mov     eax, [rbp+38h]
0x1800052d2  cmp     eax, 0E06D7363h
0x1800052d7  jnz     short loc_1800052ED
0x1800052d9  mov     rdx, [rbp+0B0h]
0x1800052e0  mov     ecx, [rbp+38h]
0x1800052e3  call    _XcptFilter_0
0x1800052e8  mov     [rbp+40h], eax
0x1800052eb  jmp     short loc_1800052F4
0x1800052ed  mov     dword ptr [rbp+40h], 0
0x1800052f4  mov     eax, [rbp+40h]
0x1800052f7  add     rsp, 20h
0x1800052fb  pop     rbp
0x1800052fc  retn
0x1800052fe  push    rbp
0x180005300  sub     rsp, 20h
0x180005304  mov     rbp, rdx
0x180005307  mov     rax, [rcx]
0x18000530a  mov     edx, [rax]
0x18000530c  mov     [rbp+0B8h], rcx
0x180005313  mov     [rbp+48h], edx
0x180005316  mov     eax, [rbp+48h]
0x180005319  cmp     eax, 0E06D7363h
0x18000531e  jnz     short loc_180005334
0x180005320  mov     rdx, [rbp+0B8h]
0x180005327  mov     ecx, [rbp+48h]
0x18000532a  call    _XcptFilter_0
0x18000532f  mov     [rbp+50h], eax
0x180005332  jmp     short loc_18000533B
0x180005334  mov     dword ptr [rbp+50h], 0
0x18000533b  mov     eax, [rbp+50h]
0x18000533e  add     rsp, 20h
0x180005342  pop     rbp
0x180005343  retn
0x180005345  push    rbp
0x180005347  sub     rsp, 20h
0x18000534b  mov     rbp, rdx
0x18000534e  mov     rax, [rcx]
0x180005351  mov     edx, [rax]
0x180005353  mov     [rbp+0C0h], rcx
0x18000535a  mov     [rbp+58h], edx
0x18000535d  mov     eax, [rbp+58h]
0x180005360  cmp     eax, 0E06D7363h
0x180005365  jnz     short loc_18000537B
0x180005367  mov     rdx, [rbp+0C0h]
0x18000536e  mov     ecx, [rbp+58h]
0x180005371  call    _XcptFilter_0
0x180005376  mov     [rbp+60h], eax
0x180005379  jmp     short loc_180005382
0x18000537b  mov     dword ptr [rbp+60h], 0
0x180005382  mov     eax, [rbp+60h]
0x180005385  add     rsp, 20h
0x180005389  pop     rbp
0x18000538a  retn
0x18000538c  push    rbp
0x18000538e  sub     rsp, 20h
0x180005392  mov     rbp, rdx
0x180005395  mov     rax, [rcx]
0x180005398  mov     edx, [rax]
0x18000539a  mov     [rbp+0C8h], rcx
0x1800053a1  mov     [rbp+68h], edx
0x1800053a4  mov     eax, [rbp+68h]
0x1800053a7  cmp     eax, 0E06D7363h
0x1800053ac  jnz     short loc_1800053C2
0x1800053ae  mov     rdx, [rbp+0C8h]
0x1800053b5  mov     ecx, [rbp+68h]
0x1800053b8  call    _XcptFilter_0
0x1800053bd  mov     [rbp+70h], eax
0x1800053c0  jmp     short loc_1800053C9
0x1800053c2  mov     dword ptr [rbp+70h], 0
0x1800053c9  mov     eax, [rbp+70h]
0x1800053cc  add     rsp, 20h
0x1800053d0  pop     rbp
0x1800053d1  retn
0x1800053d3  push    rbp
0x1800053d5  sub     rsp, 20h
0x1800053d9  mov     rbp, rdx
0x1800053dc  mov     rax, [rcx]
0x1800053df  mov     edx, [rax]
0x1800053e1  mov     [rbp+0D0h], rcx
0x1800053e8  mov     [rbp+78h], edx
0x1800053eb  mov     eax, [rbp+78h]
0x1800053ee  cmp     eax, 0E06D7363h
0x1800053f3  jnz     short loc_18000540C
0x1800053f5  mov     rdx, [rbp+0D0h]
0x1800053fc  mov     ecx, [rbp+78h]
0x1800053ff  call    _XcptFilter_0
0x180005404  mov     [rbp+80h], eax
0x18000540a  jmp     short loc_180005416
0x18000540c  mov     dword ptr [rbp+80h], 0
0x180005416  mov     eax, [rbp+80h]
0x18000541c  add     rsp, 20h
0x180005420  pop     rbp
0x180005421  retn
0x180005423  push    rbp
0x180005425  sub     rsp, 20h
0x180005429  mov     rbp, rdx
0x18000542c  mov     rax, [rcx]
0x18000542f  mov     edx, [rax]
0x180005431  mov     [rbp+0D8h], rcx
0x180005438  mov     [rbp+88h], edx
0x18000543e  mov     eax, [rbp+88h]
0x180005444  cmp     eax, 0E06D7363h
0x180005449  jnz     short loc_180005465
0x18000544b  mov     rdx, [rbp+0D8h]
0x180005452  mov     ecx, [rbp+88h]
0x180005458  call    _XcptFilter_0
0x18000545d  mov     [rbp+90h], eax
0x180005463  jmp     short loc_18000546F
0x180005465  mov     dword ptr [rbp+90h], 0
0x18000546f  mov     eax, [rbp+90h]
0x180005475  add     rsp, 20h
0x180005479  pop     rbp
0x18000547a  retn
0x18000547c  push    rbp
0x18000547e  sub     rsp, 20h
0x180005482  mov     rbp, rdx
0x180005485  mov     rax, [rcx]
0x180005488  mov     edx, [rax]
0x18000548a  mov     [rbp+0E0h], rcx
0x180005491  mov     [rbp+98h], edx
0x180005497  mov     eax, [rbp+98h]
0x18000549d  cmp     eax, 0E06D7363h
0x1800054a2  jnz     short loc_1800054BE
0x1800054a4  mov     rdx, [rbp+0E0h]
0x1800054ab  mov     ecx, [rbp+98h]
0x1800054b1  call    _XcptFilter_0
0x1800054b6  mov     [rbp+0A0h], eax
0x1800054bc  jmp     short loc_1800054C8
0x1800054be  mov     dword ptr [rbp+0A0h], 0
0x1800054c8  mov     eax, [rbp+0A0h]
0x1800054ce  add     rsp, 20h
0x1800054d2  pop     rbp
0x1800054d3  retn
0x1800054d5  push    rbp
0x1800054d7  sub     rsp, 20h
0x1800054db  mov     rbp, rdx
0x1800054de  cmp     dword ptr [rbp+118h], 1
0x1800054e5  ja      short loc_1800054F1
0x1800054e7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
