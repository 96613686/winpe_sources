# __DllMainCRTStartup

- ea: `0x180001944`
- end: `0x180001b50`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001900`

## callees

- `0x1800016d0`
- `0x180001944`
- `0x180001d1e`
- `0x180001ef8`
- `0x180014380`

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
  if ( (_DWORD)fdwReason || dword_18002379C )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800237A0 = 1;
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
            if ( dword_1800237A0 )
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
0x180001944  mov     [rsp+lpvReserved], r8
0x180001949  mov     [rsp+arg_8], edx
0x18000194d  mov     [rsp+arg_0], rcx
0x180001952  push    rbx
0x180001953  push    rsi
0x180001954  push    rdi
0x180001955  sub     rsp, 0F0h
0x18000195c  mov     edi, edx
0x18000195e  mov     rsi, rcx
0x180001961  mov     ebx, 1
0x180001966  cmp     edx, ebx
0x180001968  ja      short loc_180001970
0x18000196a  mov     cs:__native_dllmain_reason, edx
0x180001970  test    edx, edx
0x180001972  jnz     short loc_180001987
0x180001974  cmp     cs:dword_18002379C, edx
0x18000197a  jnz     short loc_180001987
0x18000197c  xor     ebx, ebx
0x18000197e  mov     [rsp+108h+var_E8], ebx
0x180001982  jmp     loc_180001B34
0x180001987  lea     eax, [rdx-1]
0x18000198a  cmp     eax, 1
0x18000198d  ja      loc_180001A14
0x180001993  mov     rax, cs:_pRawDllMain
0x18000199a  test    rax, rax
0x18000199d  jz      short loc_1800019D5
0x18000199f  cmp     edx, 1
0x1800019a2  jnz     short loc_1800019AA
0x1800019a4  mov     cs:dword_1800237A0, edx
0x1800019aa  mov     r8, [rsp+108h+lpvReserved]
0x1800019b2  call    cs:__guard_dispatch_icall_fptr
0x1800019b8  mov     ebx, eax
0x1800019ba  mov     [rsp+108h+var_E8], eax
0x1800019be  jmp     short loc_1800019D5
0x1800019c0  xor     ebx, ebx
0x1800019c2  mov     [rsp+108h+var_E8], ebx
0x1800019c6  mov     edi, [rsp+108h+arg_8]
0x1800019cd  mov     rsi, [rsp+108h+arg_0]
0x1800019d5  test    ebx, ebx
0x1800019d7  jz      loc_180001B34
0x1800019dd  mov     r8, [rsp+108h+lpvReserved]
0x1800019e5  mov     edx, edi
0x1800019e7  mov     rcx, rsi
0x1800019ea  call    _CRT_INIT
0x1800019ef  mov     ebx, eax
0x1800019f1  mov     [rsp+108h+var_E8], eax
0x1800019f5  jmp     short loc_180001A0C
0x1800019f7  xor     ebx, ebx
0x1800019f9  mov     [rsp+108h+var_E8], ebx
0x1800019fd  mov     edi, [rsp+108h+arg_8]
0x180001a04  mov     rsi, [rsp+108h+arg_0]
0x180001a0c  test    ebx, ebx
0x180001a0e  jz      loc_180001B34
0x180001a14  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180001a1c  mov     edx, edi; fdwReason
0x180001a1e  mov     rcx, rsi; hinstDLL
0x180001a21  call    DllMain
0x180001a26  mov     ebx, eax
0x180001a28  mov     [rsp+108h+var_E8], eax
0x180001a2c  jmp     short loc_180001A43
0x180001a2e  xor     ebx, ebx
0x180001a30  mov     [rsp+108h+var_E8], ebx
0x180001a34  mov     edi, [rsp+108h+arg_8]
0x180001a3b  mov     rsi, [rsp+108h+arg_0]
0x180001a43  cmp     edi, 1
0x180001a46  jnz     short loc_180001ABF
0x180001a48  test    ebx, ebx
0x180001a4a  jnz     short loc_180001ABF
0x180001a4c  xor     r8d, r8d; lpvReserved
0x180001a4f  xor     edx, edx; fdwReason
0x180001a51  mov     rcx, rsi; hinstDLL
0x180001a54  call    DllMain
0x180001a59  jmp     short loc_180001A6E
0x180001a5b  mov     edi, [rsp+108h+arg_8]
0x180001a62  mov     rsi, [rsp+108h+arg_0]
0x180001a6a  mov     ebx, [rsp+108h+var_E8]
0x180001a6e  xor     r8d, r8d
0x180001a71  xor     edx, edx
0x180001a73  mov     rcx, rsi
0x180001a76  call    _CRT_INIT
0x180001a7b  jmp     short loc_180001A90
0x180001a7d  mov     edi, [rsp+108h+arg_8]
0x180001a84  mov     rsi, [rsp+108h+arg_0]
0x180001a8c  mov     ebx, [rsp+108h+var_E8]
0x180001a90  mov     rax, cs:_pRawDllMain
0x180001a97  test    rax, rax
0x180001a9a  jz      short loc_180001ABF
0x180001a9c  xor     r8d, r8d
0x180001a9f  xor     edx, edx
0x180001aa1  mov     rcx, rsi
0x180001aa4  call    cs:__guard_dispatch_icall_fptr
0x180001aaa  jmp     short loc_180001ABF
0x180001aac  mov     edi, [rsp+108h+arg_8]
0x180001ab3  mov     rsi, [rsp+108h+arg_0]
0x180001abb  mov     ebx, [rsp+108h+var_E8]
0x180001abf  test    edi, edi
0x180001ac1  jz      short loc_180001AC8
0x180001ac3  cmp     edi, 3
0x180001ac6  jnz     short loc_180001B34
0x180001ac8  mov     r8, [rsp+108h+lpvReserved]
0x180001ad0  mov     edx, edi
0x180001ad2  mov     rcx, rsi
0x180001ad5  call    _CRT_INIT
0x180001ada  mov     ebx, eax
0x180001adc  mov     [rsp+108h+var_E8], eax
0x180001ae0  jmp     short loc_180001AF7
0x180001ae2  xor     ebx, ebx
0x180001ae4  mov     [rsp+108h+var_E8], ebx
0x180001ae8  mov     edi, [rsp+108h+arg_8]
0x180001aef  mov     rsi, [rsp+108h+arg_0]
0x180001af7  mov     rax, cs:_pRawDllMain
0x180001afe  test    rax, rax
0x180001b01  jz      short loc_180001B34
0x180001b03  cmp     cs:dword_1800237A0, 0
0x180001b0a  jz      short loc_180001B34
0x180001b0c  mov     r8, [rsp+108h+lpvReserved]
0x180001b14  mov     edx, edi
0x180001b16  mov     rcx, rsi
0x180001b19  call    cs:__guard_dispatch_icall_fptr
0x180001b1f  mov     ebx, eax
0x180001b21  mov     [rsp+108h+var_E8], eax
0x180001b25  jmp     short loc_180001B34
0x180001b27  xor     ebx, ebx
0x180001b29  mov     [rsp+108h+var_E8], ebx
0x180001b2d  mov     edi, [rsp+108h+arg_8]
0x180001b34  cmp     edi, 1
0x180001b37  ja      short loc_180001B43
0x180001b39  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001b43  mov     eax, ebx
0x180001b45  add     rsp, 0F0h
0x180001b4c  pop     rdi
0x180001b4d  pop     rsi
0x180001b4e  pop     rbx
0x180001b4f  retn
0x180014423  push    rbp
0x180014425  sub     rsp, 20h
0x180014429  mov     rbp, rdx
0x18001442c  mov     rax, [rcx]
0x18001442f  mov     edx, [rax]
0x180014431  mov     [rbp+0A8h], rcx
0x180014438  mov     [rbp+28h], edx
0x18001443b  mov     eax, [rbp+28h]
0x18001443e  cmp     eax, 0E06D7363h
0x180014443  jnz     short loc_180014459
0x180014445  mov     rdx, [rbp+0A8h]
0x18001444c  mov     ecx, [rbp+28h]
0x18001444f  call    _XcptFilter_0
0x180014454  mov     [rbp+30h], eax
0x180014457  jmp     short loc_180014460
0x180014459  mov     dword ptr [rbp+30h], 0
0x180014460  mov     eax, [rbp+30h]
0x180014463  add     rsp, 20h
0x180014467  pop     rbp
0x180014468  retn
0x18001446a  push    rbp
0x18001446c  sub     rsp, 20h
0x180014470  mov     rbp, rdx
0x180014473  mov     rax, [rcx]
0x180014476  mov     edx, [rax]
0x180014478  mov     [rbp+0B0h], rcx
0x18001447f  mov     [rbp+38h], edx
0x180014482  mov     eax, [rbp+38h]
0x180014485  cmp     eax, 0E06D7363h
0x18001448a  jnz     short loc_1800144A0
0x18001448c  mov     rdx, [rbp+0B0h]
0x180014493  mov     ecx, [rbp+38h]
0x180014496  call    _XcptFilter_0
0x18001449b  mov     [rbp+40h], eax
0x18001449e  jmp     short loc_1800144A7
0x1800144a0  mov     dword ptr [rbp+40h], 0
0x1800144a7  mov     eax, [rbp+40h]
0x1800144aa  add     rsp, 20h
0x1800144ae  pop     rbp
0x1800144af  retn
0x1800144b1  push    rbp
0x1800144b3  sub     rsp, 20h
0x1800144b7  mov     rbp, rdx
0x1800144ba  mov     rax, [rcx]
0x1800144bd  mov     edx, [rax]
0x1800144bf  mov     [rbp+0B8h], rcx
0x1800144c6  mov     [rbp+48h], edx
0x1800144c9  mov     eax, [rbp+48h]
0x1800144cc  cmp     eax, 0E06D7363h
0x1800144d1  jnz     short loc_1800144E7
0x1800144d3  mov     rdx, [rbp+0B8h]
0x1800144da  mov     ecx, [rbp+48h]
0x1800144dd  call    _XcptFilter_0
0x1800144e2  mov     [rbp+50h], eax
0x1800144e5  jmp     short loc_1800144EE
0x1800144e7  mov     dword ptr [rbp+50h], 0
0x1800144ee  mov     eax, [rbp+50h]
0x1800144f1  add     rsp, 20h
0x1800144f5  pop     rbp
0x1800144f6  retn
0x1800144f8  push    rbp
0x1800144fa  sub     rsp, 20h
0x1800144fe  mov     rbp, rdx
0x180014501  mov     rax, [rcx]
0x180014504  mov     edx, [rax]
0x180014506  mov     [rbp+0C0h], rcx
0x18001450d  mov     [rbp+58h], edx
0x180014510  mov     eax, [rbp+58h]
0x180014513  cmp     eax, 0E06D7363h
0x180014518  jnz     short loc_18001452E
0x18001451a  mov     rdx, [rbp+0C0h]
0x180014521  mov     ecx, [rbp+58h]
0x180014524  call    _XcptFilter_0
0x180014529  mov     [rbp+60h], eax
0x18001452c  jmp     short loc_180014535
0x18001452e  mov     dword ptr [rbp+60h], 0
0x180014535  mov     eax, [rbp+60h]
0x180014538  add     rsp, 20h
0x18001453c  pop     rbp
0x18001453d  retn
0x18001453f  push    rbp
0x180014541  sub     rsp, 20h
0x180014545  mov     rbp, rdx
0x180014548  mov     rax, [rcx]
0x18001454b  mov     edx, [rax]
0x18001454d  mov     [rbp+0C8h], rcx
0x180014554  mov     [rbp+68h], edx
0x180014557  mov     eax, [rbp+68h]
0x18001455a  cmp     eax, 0E06D7363h
0x18001455f  jnz     short loc_180014575
0x180014561  mov     rdx, [rbp+0C8h]
0x180014568  mov     ecx, [rbp+68h]
0x18001456b  call    _XcptFilter_0
0x180014570  mov     [rbp+70h], eax
0x180014573  jmp     short loc_18001457C
0x180014575  mov     dword ptr [rbp+70h], 0
0x18001457c  mov     eax, [rbp+70h]
0x18001457f  add     rsp, 20h
0x180014583  pop     rbp
0x180014584  retn
0x180014586  push    rbp
0x180014588  sub     rsp, 20h
0x18001458c  mov     rbp, rdx
0x18001458f  mov     rax, [rcx]
0x180014592  mov     edx, [rax]
0x180014594  mov     [rbp+0D0h], rcx
0x18001459b  mov     [rbp+78h], edx
0x18001459e  mov     eax, [rbp+78h]
0x1800145a1  cmp     eax, 0E06D7363h
0x1800145a6  jnz     short loc_1800145BF
0x1800145a8  mov     rdx, [rbp+0D0h]
0x1800145af  mov     ecx, [rbp+78h]
0x1800145b2  call    _XcptFilter_0
0x1800145b7  mov     [rbp+80h], eax
0x1800145bd  jmp     short loc_1800145C9
0x1800145bf  mov     dword ptr [rbp+80h], 0
0x1800145c9  mov     eax, [rbp+80h]
0x1800145cf  add     rsp, 20h
0x1800145d3  pop     rbp
0x1800145d4  retn
0x1800145d6  push    rbp
0x1800145d8  sub     rsp, 20h
0x1800145dc  mov     rbp, rdx
0x1800145df  mov     rax, [rcx]
0x1800145e2  mov     edx, [rax]
0x1800145e4  mov     [rbp+0D8h], rcx
0x1800145eb  mov     [rbp+88h], edx
0x1800145f1  mov     eax, [rbp+88h]
0x1800145f7  cmp     eax, 0E06D7363h
0x1800145fc  jnz     short loc_180014618
0x1800145fe  mov     rdx, [rbp+0D8h]
0x180014605  mov     ecx, [rbp+88h]
0x18001460b  call    _XcptFilter_0
0x180014610  mov     [rbp+90h], eax
0x180014616  jmp     short loc_180014622
0x180014618  mov     dword ptr [rbp+90h], 0
0x180014622  mov     eax, [rbp+90h]
0x180014628  add     rsp, 20h
0x18001462c  pop     rbp
0x18001462d  retn
0x18001462f  push    rbp
0x180014631  sub     rsp, 20h
0x180014635  mov     rbp, rdx
0x180014638  mov     rax, [rcx]
0x18001463b  mov     edx, [rax]
0x18001463d  mov     [rbp+0E0h], rcx
0x180014644  mov     [rbp+98h], edx
0x18001464a  mov     eax, [rbp+98h]
0x180014650  cmp     eax, 0E06D7363h
0x180014655  jnz     short loc_180014671
0x180014657  mov     rdx, [rbp+0E0h]
0x18001465e  mov     ecx, [rbp+98h]
0x180014664  call    _XcptFilter_0
0x180014669  mov     [rbp+0A0h], eax
0x18001466f  jmp     short loc_18001467B
0x180014671  mov     dword ptr [rbp+0A0h], 0
0x18001467b  mov     eax, [rbp+0A0h]
0x180014681  add     rsp, 20h
0x180014685  pop     rbp
0x180014686  retn
0x180014688  push    rbp
0x18001468a  sub     rsp, 20h
0x18001468e  mov     rbp, rdx
0x180014691  cmp     dword ptr [rbp+118h], 1
0x180014698  ja      short loc_1800146A4
0x18001469a  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
