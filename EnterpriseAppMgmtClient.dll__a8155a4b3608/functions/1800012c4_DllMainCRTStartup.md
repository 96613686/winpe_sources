# __DllMainCRTStartup

- ea: `0x1800012c4`
- end: `0x1800014d0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001280`

## callees

- `0x180001050`
- `0x1800012c4`
- `0x1800014d6`
- `0x1800017e4`
- `0x180001830`

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
  if ( (_DWORD)fdwReason || dword_1800060A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800060A4 = 1;
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
            if ( dword_1800060A4 )
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
0x1800012f4  cmp     cs:dword_1800060A0, edx
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
0x180001324  mov     cs:dword_1800060A4, edx
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
0x180001483  cmp     cs:dword_1800060A4, 0
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
0x180001870  push    rbp
0x180001872  sub     rsp, 20h
0x180001876  mov     rbp, rdx
0x180001879  mov     rax, [rcx]
0x18000187c  mov     edx, [rax]
0x18000187e  mov     [rbp+0A8h], rcx
0x180001885  mov     [rbp+28h], edx
0x180001888  mov     eax, [rbp+28h]
0x18000188b  cmp     eax, 0E06D7363h
0x180001890  jnz     short loc_1800018A6
0x180001892  mov     rdx, [rbp+0A8h]
0x180001899  mov     ecx, [rbp+28h]
0x18000189c  call    _XcptFilter_0
0x1800018a1  mov     [rbp+30h], eax
0x1800018a4  jmp     short loc_1800018AD
0x1800018a6  mov     dword ptr [rbp+30h], 0
0x1800018ad  mov     eax, [rbp+30h]
0x1800018b0  add     rsp, 20h
0x1800018b4  pop     rbp
0x1800018b5  retn
0x1800018b7  push    rbp
0x1800018b9  sub     rsp, 20h
0x1800018bd  mov     rbp, rdx
0x1800018c0  mov     rax, [rcx]
0x1800018c3  mov     edx, [rax]
0x1800018c5  mov     [rbp+0B0h], rcx
0x1800018cc  mov     [rbp+38h], edx
0x1800018cf  mov     eax, [rbp+38h]
0x1800018d2  cmp     eax, 0E06D7363h
0x1800018d7  jnz     short loc_1800018ED
0x1800018d9  mov     rdx, [rbp+0B0h]
0x1800018e0  mov     ecx, [rbp+38h]
0x1800018e3  call    _XcptFilter_0
0x1800018e8  mov     [rbp+40h], eax
0x1800018eb  jmp     short loc_1800018F4
0x1800018ed  mov     dword ptr [rbp+40h], 0
0x1800018f4  mov     eax, [rbp+40h]
0x1800018f7  add     rsp, 20h
0x1800018fb  pop     rbp
0x1800018fc  retn
0x1800018fe  push    rbp
0x180001900  sub     rsp, 20h
0x180001904  mov     rbp, rdx
0x180001907  mov     rax, [rcx]
0x18000190a  mov     edx, [rax]
0x18000190c  mov     [rbp+0B8h], rcx
0x180001913  mov     [rbp+48h], edx
0x180001916  mov     eax, [rbp+48h]
0x180001919  cmp     eax, 0E06D7363h
0x18000191e  jnz     short loc_180001934
0x180001920  mov     rdx, [rbp+0B8h]
0x180001927  mov     ecx, [rbp+48h]
0x18000192a  call    _XcptFilter_0
0x18000192f  mov     [rbp+50h], eax
0x180001932  jmp     short loc_18000193B
0x180001934  mov     dword ptr [rbp+50h], 0
0x18000193b  mov     eax, [rbp+50h]
0x18000193e  add     rsp, 20h
0x180001942  pop     rbp
0x180001943  retn
0x180001945  push    rbp
0x180001947  sub     rsp, 20h
0x18000194b  mov     rbp, rdx
0x18000194e  mov     rax, [rcx]
0x180001951  mov     edx, [rax]
0x180001953  mov     [rbp+0C0h], rcx
0x18000195a  mov     [rbp+58h], edx
0x18000195d  mov     eax, [rbp+58h]
0x180001960  cmp     eax, 0E06D7363h
0x180001965  jnz     short loc_18000197B
0x180001967  mov     rdx, [rbp+0C0h]
0x18000196e  mov     ecx, [rbp+58h]
0x180001971  call    _XcptFilter_0
0x180001976  mov     [rbp+60h], eax
0x180001979  jmp     short loc_180001982
0x18000197b  mov     dword ptr [rbp+60h], 0
0x180001982  mov     eax, [rbp+60h]
0x180001985  add     rsp, 20h
0x180001989  pop     rbp
0x18000198a  retn
0x18000198c  push    rbp
0x18000198e  sub     rsp, 20h
0x180001992  mov     rbp, rdx
0x180001995  mov     rax, [rcx]
0x180001998  mov     edx, [rax]
0x18000199a  mov     [rbp+0C8h], rcx
0x1800019a1  mov     [rbp+68h], edx
0x1800019a4  mov     eax, [rbp+68h]
0x1800019a7  cmp     eax, 0E06D7363h
0x1800019ac  jnz     short loc_1800019C2
0x1800019ae  mov     rdx, [rbp+0C8h]
0x1800019b5  mov     ecx, [rbp+68h]
0x1800019b8  call    _XcptFilter_0
0x1800019bd  mov     [rbp+70h], eax
0x1800019c0  jmp     short loc_1800019C9
0x1800019c2  mov     dword ptr [rbp+70h], 0
0x1800019c9  mov     eax, [rbp+70h]
0x1800019cc  add     rsp, 20h
0x1800019d0  pop     rbp
0x1800019d1  retn
0x1800019d3  push    rbp
0x1800019d5  sub     rsp, 20h
0x1800019d9  mov     rbp, rdx
0x1800019dc  mov     rax, [rcx]
0x1800019df  mov     edx, [rax]
0x1800019e1  mov     [rbp+0D0h], rcx
0x1800019e8  mov     [rbp+78h], edx
0x1800019eb  mov     eax, [rbp+78h]
0x1800019ee  cmp     eax, 0E06D7363h
0x1800019f3  jnz     short loc_180001A0C
0x1800019f5  mov     rdx, [rbp+0D0h]
0x1800019fc  mov     ecx, [rbp+78h]
0x1800019ff  call    _XcptFilter_0
0x180001a04  mov     [rbp+80h], eax
0x180001a0a  jmp     short loc_180001A16
0x180001a0c  mov     dword ptr [rbp+80h], 0
0x180001a16  mov     eax, [rbp+80h]
0x180001a1c  add     rsp, 20h
0x180001a20  pop     rbp
0x180001a21  retn
0x180001a23  push    rbp
0x180001a25  sub     rsp, 20h
0x180001a29  mov     rbp, rdx
0x180001a2c  mov     rax, [rcx]
0x180001a2f  mov     edx, [rax]
0x180001a31  mov     [rbp+0D8h], rcx
0x180001a38  mov     [rbp+88h], edx
0x180001a3e  mov     eax, [rbp+88h]
0x180001a44  cmp     eax, 0E06D7363h
0x180001a49  jnz     short loc_180001A65
0x180001a4b  mov     rdx, [rbp+0D8h]
0x180001a52  mov     ecx, [rbp+88h]
0x180001a58  call    _XcptFilter_0
0x180001a5d  mov     [rbp+90h], eax
0x180001a63  jmp     short loc_180001A6F
0x180001a65  mov     dword ptr [rbp+90h], 0
0x180001a6f  mov     eax, [rbp+90h]
0x180001a75  add     rsp, 20h
0x180001a79  pop     rbp
0x180001a7a  retn
0x180001a7c  push    rbp
0x180001a7e  sub     rsp, 20h
0x180001a82  mov     rbp, rdx
0x180001a85  mov     rax, [rcx]
0x180001a88  mov     edx, [rax]
0x180001a8a  mov     [rbp+0E0h], rcx
0x180001a91  mov     [rbp+98h], edx
0x180001a97  mov     eax, [rbp+98h]
0x180001a9d  cmp     eax, 0E06D7363h
0x180001aa2  jnz     short loc_180001ABE
0x180001aa4  mov     rdx, [rbp+0E0h]
0x180001aab  mov     ecx, [rbp+98h]
0x180001ab1  call    _XcptFilter_0
0x180001ab6  mov     [rbp+0A0h], eax
0x180001abc  jmp     short loc_180001AC8
0x180001abe  mov     dword ptr [rbp+0A0h], 0
0x180001ac8  mov     eax, [rbp+0A0h]
0x180001ace  add     rsp, 20h
0x180001ad2  pop     rbp
0x180001ad3  retn
0x180001ad5  push    rbp
0x180001ad7  sub     rsp, 20h
0x180001adb  mov     rbp, rdx
0x180001ade  cmp     dword ptr [rbp+118h], 1
0x180001ae5  ja      short loc_180001AF1
0x180001ae7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
