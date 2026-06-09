# __DllMainCRTStartup

- ea: `0x1800028b4`
- end: `0x180002ac0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180002870`

## callees

- `0x180002640`
- `0x1800028b4`
- `0x180002bd8`
- `0x18000acb0`
- `0x18001b380`

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
  if ( (_DWORD)fdwReason || dword_18002A980 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18002A984 = 1;
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
            if ( dword_18002A984 )
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
0x1800028b4  mov     [rsp+lpvReserved], r8
0x1800028b9  mov     [rsp+arg_8], edx
0x1800028bd  mov     [rsp+arg_0], rcx
0x1800028c2  push    rbx
0x1800028c3  push    rsi
0x1800028c4  push    rdi
0x1800028c5  sub     rsp, 0F0h
0x1800028cc  mov     edi, edx
0x1800028ce  mov     rsi, rcx
0x1800028d1  mov     ebx, 1
0x1800028d6  cmp     edx, ebx
0x1800028d8  ja      short loc_1800028E0
0x1800028da  mov     cs:__native_dllmain_reason, edx
0x1800028e0  test    edx, edx
0x1800028e2  jnz     short loc_1800028F7
0x1800028e4  cmp     cs:dword_18002A980, edx
0x1800028ea  jnz     short loc_1800028F7
0x1800028ec  xor     ebx, ebx
0x1800028ee  mov     [rsp+108h+var_E8], ebx
0x1800028f2  jmp     loc_180002AA4
0x1800028f7  lea     eax, [rdx-1]
0x1800028fa  cmp     eax, 1
0x1800028fd  ja      loc_180002984
0x180002903  mov     rax, cs:_pRawDllMain
0x18000290a  test    rax, rax
0x18000290d  jz      short loc_180002945
0x18000290f  cmp     edx, 1
0x180002912  jnz     short loc_18000291A
0x180002914  mov     cs:dword_18002A984, edx
0x18000291a  mov     r8, [rsp+108h+lpvReserved]
0x180002922  call    cs:__guard_dispatch_icall_fptr
0x180002928  mov     ebx, eax
0x18000292a  mov     [rsp+108h+var_E8], eax
0x18000292e  jmp     short loc_180002945
0x180002930  xor     ebx, ebx
0x180002932  mov     [rsp+108h+var_E8], ebx
0x180002936  mov     edi, [rsp+108h+arg_8]
0x18000293d  mov     rsi, [rsp+108h+arg_0]
0x180002945  test    ebx, ebx
0x180002947  jz      loc_180002AA4
0x18000294d  mov     r8, [rsp+108h+lpvReserved]
0x180002955  mov     edx, edi
0x180002957  mov     rcx, rsi
0x18000295a  call    _CRT_INIT
0x18000295f  mov     ebx, eax
0x180002961  mov     [rsp+108h+var_E8], eax
0x180002965  jmp     short loc_18000297C
0x180002967  xor     ebx, ebx
0x180002969  mov     [rsp+108h+var_E8], ebx
0x18000296d  mov     edi, [rsp+108h+arg_8]
0x180002974  mov     rsi, [rsp+108h+arg_0]
0x18000297c  test    ebx, ebx
0x18000297e  jz      loc_180002AA4
0x180002984  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000298c  mov     edx, edi; fdwReason
0x18000298e  mov     rcx, rsi; hinstDLL
0x180002991  call    DllMain
0x180002996  mov     ebx, eax
0x180002998  mov     [rsp+108h+var_E8], eax
0x18000299c  jmp     short loc_1800029B3
0x18000299e  xor     ebx, ebx
0x1800029a0  mov     [rsp+108h+var_E8], ebx
0x1800029a4  mov     edi, [rsp+108h+arg_8]
0x1800029ab  mov     rsi, [rsp+108h+arg_0]
0x1800029b3  cmp     edi, 1
0x1800029b6  jnz     short loc_180002A2F
0x1800029b8  test    ebx, ebx
0x1800029ba  jnz     short loc_180002A2F
0x1800029bc  xor     r8d, r8d; lpvReserved
0x1800029bf  xor     edx, edx; fdwReason
0x1800029c1  mov     rcx, rsi; hinstDLL
0x1800029c4  call    DllMain
0x1800029c9  jmp     short loc_1800029DE
0x1800029cb  mov     edi, [rsp+108h+arg_8]
0x1800029d2  mov     rsi, [rsp+108h+arg_0]
0x1800029da  mov     ebx, [rsp+108h+var_E8]
0x1800029de  xor     r8d, r8d
0x1800029e1  xor     edx, edx
0x1800029e3  mov     rcx, rsi
0x1800029e6  call    _CRT_INIT
0x1800029eb  jmp     short loc_180002A00
0x1800029ed  mov     edi, [rsp+108h+arg_8]
0x1800029f4  mov     rsi, [rsp+108h+arg_0]
0x1800029fc  mov     ebx, [rsp+108h+var_E8]
0x180002a00  mov     rax, cs:_pRawDllMain
0x180002a07  test    rax, rax
0x180002a0a  jz      short loc_180002A2F
0x180002a0c  xor     r8d, r8d
0x180002a0f  xor     edx, edx
0x180002a11  mov     rcx, rsi
0x180002a14  call    cs:__guard_dispatch_icall_fptr
0x180002a1a  jmp     short loc_180002A2F
0x180002a1c  mov     edi, [rsp+108h+arg_8]
0x180002a23  mov     rsi, [rsp+108h+arg_0]
0x180002a2b  mov     ebx, [rsp+108h+var_E8]
0x180002a2f  test    edi, edi
0x180002a31  jz      short loc_180002A38
0x180002a33  cmp     edi, 3
0x180002a36  jnz     short loc_180002AA4
0x180002a38  mov     r8, [rsp+108h+lpvReserved]
0x180002a40  mov     edx, edi
0x180002a42  mov     rcx, rsi
0x180002a45  call    _CRT_INIT
0x180002a4a  mov     ebx, eax
0x180002a4c  mov     [rsp+108h+var_E8], eax
0x180002a50  jmp     short loc_180002A67
0x180002a52  xor     ebx, ebx
0x180002a54  mov     [rsp+108h+var_E8], ebx
0x180002a58  mov     edi, [rsp+108h+arg_8]
0x180002a5f  mov     rsi, [rsp+108h+arg_0]
0x180002a67  mov     rax, cs:_pRawDllMain
0x180002a6e  test    rax, rax
0x180002a71  jz      short loc_180002AA4
0x180002a73  cmp     cs:dword_18002A984, 0
0x180002a7a  jz      short loc_180002AA4
0x180002a7c  mov     r8, [rsp+108h+lpvReserved]
0x180002a84  mov     edx, edi
0x180002a86  mov     rcx, rsi
0x180002a89  call    cs:__guard_dispatch_icall_fptr
0x180002a8f  mov     ebx, eax
0x180002a91  mov     [rsp+108h+var_E8], eax
0x180002a95  jmp     short loc_180002AA4
0x180002a97  xor     ebx, ebx
0x180002a99  mov     [rsp+108h+var_E8], ebx
0x180002a9d  mov     edi, [rsp+108h+arg_8]
0x180002aa4  cmp     edi, 1
0x180002aa7  ja      short loc_180002AB3
0x180002aa9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180002ab3  mov     eax, ebx
0x180002ab5  add     rsp, 0F0h
0x180002abc  pop     rdi
0x180002abd  pop     rsi
0x180002abe  pop     rbx
0x180002abf  retn
0x18001b450  push    rbp
0x18001b452  sub     rsp, 20h
0x18001b456  mov     rbp, rdx
0x18001b459  mov     rax, [rcx]
0x18001b45c  mov     edx, [rax]
0x18001b45e  mov     [rbp+0A8h], rcx
0x18001b465  mov     [rbp+28h], edx
0x18001b468  mov     eax, [rbp+28h]
0x18001b46b  cmp     eax, 0E06D7363h
0x18001b470  jnz     short loc_18001B486
0x18001b472  mov     rdx, [rbp+0A8h]
0x18001b479  mov     ecx, [rbp+28h]
0x18001b47c  call    _XcptFilter_0
0x18001b481  mov     [rbp+30h], eax
0x18001b484  jmp     short loc_18001B48D
0x18001b486  mov     dword ptr [rbp+30h], 0
0x18001b48d  mov     eax, [rbp+30h]
0x18001b490  add     rsp, 20h
0x18001b494  pop     rbp
0x18001b495  retn
0x18001b497  push    rbp
0x18001b499  sub     rsp, 20h
0x18001b49d  mov     rbp, rdx
0x18001b4a0  mov     rax, [rcx]
0x18001b4a3  mov     edx, [rax]
0x18001b4a5  mov     [rbp+0B0h], rcx
0x18001b4ac  mov     [rbp+38h], edx
0x18001b4af  mov     eax, [rbp+38h]
0x18001b4b2  cmp     eax, 0E06D7363h
0x18001b4b7  jnz     short loc_18001B4CD
0x18001b4b9  mov     rdx, [rbp+0B0h]
0x18001b4c0  mov     ecx, [rbp+38h]
0x18001b4c3  call    _XcptFilter_0
0x18001b4c8  mov     [rbp+40h], eax
0x18001b4cb  jmp     short loc_18001B4D4
0x18001b4cd  mov     dword ptr [rbp+40h], 0
0x18001b4d4  mov     eax, [rbp+40h]
0x18001b4d7  add     rsp, 20h
0x18001b4db  pop     rbp
0x18001b4dc  retn
0x18001b4de  push    rbp
0x18001b4e0  sub     rsp, 20h
0x18001b4e4  mov     rbp, rdx
0x18001b4e7  mov     rax, [rcx]
0x18001b4ea  mov     edx, [rax]
0x18001b4ec  mov     [rbp+0B8h], rcx
0x18001b4f3  mov     [rbp+48h], edx
0x18001b4f6  mov     eax, [rbp+48h]
0x18001b4f9  cmp     eax, 0E06D7363h
0x18001b4fe  jnz     short loc_18001B514
0x18001b500  mov     rdx, [rbp+0B8h]
0x18001b507  mov     ecx, [rbp+48h]
0x18001b50a  call    _XcptFilter_0
0x18001b50f  mov     [rbp+50h], eax
0x18001b512  jmp     short loc_18001B51B
0x18001b514  mov     dword ptr [rbp+50h], 0
0x18001b51b  mov     eax, [rbp+50h]
0x18001b51e  add     rsp, 20h
0x18001b522  pop     rbp
0x18001b523  retn
0x18001b525  push    rbp
0x18001b527  sub     rsp, 20h
0x18001b52b  mov     rbp, rdx
0x18001b52e  mov     rax, [rcx]
0x18001b531  mov     edx, [rax]
0x18001b533  mov     [rbp+0C0h], rcx
0x18001b53a  mov     [rbp+58h], edx
0x18001b53d  mov     eax, [rbp+58h]
0x18001b540  cmp     eax, 0E06D7363h
0x18001b545  jnz     short loc_18001B55B
0x18001b547  mov     rdx, [rbp+0C0h]
0x18001b54e  mov     ecx, [rbp+58h]
0x18001b551  call    _XcptFilter_0
0x18001b556  mov     [rbp+60h], eax
0x18001b559  jmp     short loc_18001B562
0x18001b55b  mov     dword ptr [rbp+60h], 0
0x18001b562  mov     eax, [rbp+60h]
0x18001b565  add     rsp, 20h
0x18001b569  pop     rbp
0x18001b56a  retn
0x18001b56c  push    rbp
0x18001b56e  sub     rsp, 20h
0x18001b572  mov     rbp, rdx
0x18001b575  mov     rax, [rcx]
0x18001b578  mov     edx, [rax]
0x18001b57a  mov     [rbp+0C8h], rcx
0x18001b581  mov     [rbp+68h], edx
0x18001b584  mov     eax, [rbp+68h]
0x18001b587  cmp     eax, 0E06D7363h
0x18001b58c  jnz     short loc_18001B5A2
0x18001b58e  mov     rdx, [rbp+0C8h]
0x18001b595  mov     ecx, [rbp+68h]
0x18001b598  call    _XcptFilter_0
0x18001b59d  mov     [rbp+70h], eax
0x18001b5a0  jmp     short loc_18001B5A9
0x18001b5a2  mov     dword ptr [rbp+70h], 0
0x18001b5a9  mov     eax, [rbp+70h]
0x18001b5ac  add     rsp, 20h
0x18001b5b0  pop     rbp
0x18001b5b1  retn
0x18001b5b3  push    rbp
0x18001b5b5  sub     rsp, 20h
0x18001b5b9  mov     rbp, rdx
0x18001b5bc  mov     rax, [rcx]
0x18001b5bf  mov     edx, [rax]
0x18001b5c1  mov     [rbp+0D0h], rcx
0x18001b5c8  mov     [rbp+78h], edx
0x18001b5cb  mov     eax, [rbp+78h]
0x18001b5ce  cmp     eax, 0E06D7363h
0x18001b5d3  jnz     short loc_18001B5EC
0x18001b5d5  mov     rdx, [rbp+0D0h]
0x18001b5dc  mov     ecx, [rbp+78h]
0x18001b5df  call    _XcptFilter_0
0x18001b5e4  mov     [rbp+80h], eax
0x18001b5ea  jmp     short loc_18001B5F6
0x18001b5ec  mov     dword ptr [rbp+80h], 0
0x18001b5f6  mov     eax, [rbp+80h]
0x18001b5fc  add     rsp, 20h
0x18001b600  pop     rbp
0x18001b601  retn
0x18001b603  push    rbp
0x18001b605  sub     rsp, 20h
0x18001b609  mov     rbp, rdx
0x18001b60c  mov     rax, [rcx]
0x18001b60f  mov     edx, [rax]
0x18001b611  mov     [rbp+0D8h], rcx
0x18001b618  mov     [rbp+88h], edx
0x18001b61e  mov     eax, [rbp+88h]
0x18001b624  cmp     eax, 0E06D7363h
0x18001b629  jnz     short loc_18001B645
0x18001b62b  mov     rdx, [rbp+0D8h]
0x18001b632  mov     ecx, [rbp+88h]
0x18001b638  call    _XcptFilter_0
0x18001b63d  mov     [rbp+90h], eax
0x18001b643  jmp     short loc_18001B64F
0x18001b645  mov     dword ptr [rbp+90h], 0
0x18001b64f  mov     eax, [rbp+90h]
0x18001b655  add     rsp, 20h
0x18001b659  pop     rbp
0x18001b65a  retn
0x18001b65c  push    rbp
0x18001b65e  sub     rsp, 20h
0x18001b662  mov     rbp, rdx
0x18001b665  mov     rax, [rcx]
0x18001b668  mov     edx, [rax]
0x18001b66a  mov     [rbp+0E0h], rcx
0x18001b671  mov     [rbp+98h], edx
0x18001b677  mov     eax, [rbp+98h]
0x18001b67d  cmp     eax, 0E06D7363h
0x18001b682  jnz     short loc_18001B69E
0x18001b684  mov     rdx, [rbp+0E0h]
0x18001b68b  mov     ecx, [rbp+98h]
0x18001b691  call    _XcptFilter_0
0x18001b696  mov     [rbp+0A0h], eax
0x18001b69c  jmp     short loc_18001B6A8
0x18001b69e  mov     dword ptr [rbp+0A0h], 0
0x18001b6a8  mov     eax, [rbp+0A0h]
0x18001b6ae  add     rsp, 20h
0x18001b6b2  pop     rbp
0x18001b6b3  retn
0x18001b6b5  push    rbp
0x18001b6b7  sub     rsp, 20h
0x18001b6bb  mov     rbp, rdx
0x18001b6be  cmp     dword ptr [rbp+118h], 1
0x18001b6c5  ja      short loc_18001B6D1
0x18001b6c7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
