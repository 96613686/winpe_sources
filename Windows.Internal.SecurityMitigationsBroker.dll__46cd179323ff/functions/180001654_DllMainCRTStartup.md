# __DllMainCRTStartup

- ea: `0x180001654`
- end: `0x180001860`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001610`

## callees

- `0x1800013e0`
- `0x180001654`
- `0x180001968`
- `0x180004210`
- `0x1800069c0`

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
  if ( (_DWORD)fdwReason || dword_18000C180 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18000C184 = 1;
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
            if ( dword_18000C184 )
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
0x180001654  mov     [rsp+lpvReserved], r8
0x180001659  mov     [rsp+arg_8], edx
0x18000165d  mov     [rsp+arg_0], rcx
0x180001662  push    rbx
0x180001663  push    rsi
0x180001664  push    rdi
0x180001665  sub     rsp, 0F0h
0x18000166c  mov     edi, edx
0x18000166e  mov     rsi, rcx
0x180001671  mov     ebx, 1
0x180001676  cmp     edx, ebx
0x180001678  ja      short loc_180001680
0x18000167a  mov     cs:__native_dllmain_reason, edx
0x180001680  test    edx, edx
0x180001682  jnz     short loc_180001697
0x180001684  cmp     cs:dword_18000C180, edx
0x18000168a  jnz     short loc_180001697
0x18000168c  xor     ebx, ebx
0x18000168e  mov     [rsp+108h+var_E8], ebx
0x180001692  jmp     loc_180001844
0x180001697  lea     eax, [rdx-1]
0x18000169a  cmp     eax, 1
0x18000169d  ja      loc_180001724
0x1800016a3  mov     rax, cs:_pRawDllMain
0x1800016aa  test    rax, rax
0x1800016ad  jz      short loc_1800016E5
0x1800016af  cmp     edx, 1
0x1800016b2  jnz     short loc_1800016BA
0x1800016b4  mov     cs:dword_18000C184, edx
0x1800016ba  mov     r8, [rsp+108h+lpvReserved]
0x1800016c2  call    cs:__guard_dispatch_icall_fptr
0x1800016c8  mov     ebx, eax
0x1800016ca  mov     [rsp+108h+var_E8], eax
0x1800016ce  jmp     short loc_1800016E5
0x1800016d0  xor     ebx, ebx
0x1800016d2  mov     [rsp+108h+var_E8], ebx
0x1800016d6  mov     edi, [rsp+108h+arg_8]
0x1800016dd  mov     rsi, [rsp+108h+arg_0]
0x1800016e5  test    ebx, ebx
0x1800016e7  jz      loc_180001844
0x1800016ed  mov     r8, [rsp+108h+lpvReserved]
0x1800016f5  mov     edx, edi
0x1800016f7  mov     rcx, rsi
0x1800016fa  call    _CRT_INIT
0x1800016ff  mov     ebx, eax
0x180001701  mov     [rsp+108h+var_E8], eax
0x180001705  jmp     short loc_18000171C
0x180001707  xor     ebx, ebx
0x180001709  mov     [rsp+108h+var_E8], ebx
0x18000170d  mov     edi, [rsp+108h+arg_8]
0x180001714  mov     rsi, [rsp+108h+arg_0]
0x18000171c  test    ebx, ebx
0x18000171e  jz      loc_180001844
0x180001724  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000172c  mov     edx, edi; fdwReason
0x18000172e  mov     rcx, rsi; hinstDLL
0x180001731  call    DllMain
0x180001736  mov     ebx, eax
0x180001738  mov     [rsp+108h+var_E8], eax
0x18000173c  jmp     short loc_180001753
0x18000173e  xor     ebx, ebx
0x180001740  mov     [rsp+108h+var_E8], ebx
0x180001744  mov     edi, [rsp+108h+arg_8]
0x18000174b  mov     rsi, [rsp+108h+arg_0]
0x180001753  cmp     edi, 1
0x180001756  jnz     short loc_1800017CF
0x180001758  test    ebx, ebx
0x18000175a  jnz     short loc_1800017CF
0x18000175c  xor     r8d, r8d; lpvReserved
0x18000175f  xor     edx, edx; fdwReason
0x180001761  mov     rcx, rsi; hinstDLL
0x180001764  call    DllMain
0x180001769  jmp     short loc_18000177E
0x18000176b  mov     edi, [rsp+108h+arg_8]
0x180001772  mov     rsi, [rsp+108h+arg_0]
0x18000177a  mov     ebx, [rsp+108h+var_E8]
0x18000177e  xor     r8d, r8d
0x180001781  xor     edx, edx
0x180001783  mov     rcx, rsi
0x180001786  call    _CRT_INIT
0x18000178b  jmp     short loc_1800017A0
0x18000178d  mov     edi, [rsp+108h+arg_8]
0x180001794  mov     rsi, [rsp+108h+arg_0]
0x18000179c  mov     ebx, [rsp+108h+var_E8]
0x1800017a0  mov     rax, cs:_pRawDllMain
0x1800017a7  test    rax, rax
0x1800017aa  jz      short loc_1800017CF
0x1800017ac  xor     r8d, r8d
0x1800017af  xor     edx, edx
0x1800017b1  mov     rcx, rsi
0x1800017b4  call    cs:__guard_dispatch_icall_fptr
0x1800017ba  jmp     short loc_1800017CF
0x1800017bc  mov     edi, [rsp+108h+arg_8]
0x1800017c3  mov     rsi, [rsp+108h+arg_0]
0x1800017cb  mov     ebx, [rsp+108h+var_E8]
0x1800017cf  test    edi, edi
0x1800017d1  jz      short loc_1800017D8
0x1800017d3  cmp     edi, 3
0x1800017d6  jnz     short loc_180001844
0x1800017d8  mov     r8, [rsp+108h+lpvReserved]
0x1800017e0  mov     edx, edi
0x1800017e2  mov     rcx, rsi
0x1800017e5  call    _CRT_INIT
0x1800017ea  mov     ebx, eax
0x1800017ec  mov     [rsp+108h+var_E8], eax
0x1800017f0  jmp     short loc_180001807
0x1800017f2  xor     ebx, ebx
0x1800017f4  mov     [rsp+108h+var_E8], ebx
0x1800017f8  mov     edi, [rsp+108h+arg_8]
0x1800017ff  mov     rsi, [rsp+108h+arg_0]
0x180001807  mov     rax, cs:_pRawDllMain
0x18000180e  test    rax, rax
0x180001811  jz      short loc_180001844
0x180001813  cmp     cs:dword_18000C184, 0
0x18000181a  jz      short loc_180001844
0x18000181c  mov     r8, [rsp+108h+lpvReserved]
0x180001824  mov     edx, edi
0x180001826  mov     rcx, rsi
0x180001829  call    cs:__guard_dispatch_icall_fptr
0x18000182f  mov     ebx, eax
0x180001831  mov     [rsp+108h+var_E8], eax
0x180001835  jmp     short loc_180001844
0x180001837  xor     ebx, ebx
0x180001839  mov     [rsp+108h+var_E8], ebx
0x18000183d  mov     edi, [rsp+108h+arg_8]
0x180001844  cmp     edi, 1
0x180001847  ja      short loc_180001853
0x180001849  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001853  mov     eax, ebx
0x180001855  add     rsp, 0F0h
0x18000185c  pop     rdi
0x18000185d  pop     rsi
0x18000185e  pop     rbx
0x18000185f  retn
0x180006a90  push    rbp
0x180006a92  sub     rsp, 20h
0x180006a96  mov     rbp, rdx
0x180006a99  mov     rax, [rcx]
0x180006a9c  mov     edx, [rax]
0x180006a9e  mov     [rbp+0A8h], rcx
0x180006aa5  mov     [rbp+28h], edx
0x180006aa8  mov     eax, [rbp+28h]
0x180006aab  cmp     eax, 0E06D7363h
0x180006ab0  jnz     short loc_180006AC6
0x180006ab2  mov     rdx, [rbp+0A8h]
0x180006ab9  mov     ecx, [rbp+28h]
0x180006abc  call    _XcptFilter_0
0x180006ac1  mov     [rbp+30h], eax
0x180006ac4  jmp     short loc_180006ACD
0x180006ac6  mov     dword ptr [rbp+30h], 0
0x180006acd  mov     eax, [rbp+30h]
0x180006ad0  add     rsp, 20h
0x180006ad4  pop     rbp
0x180006ad5  retn
0x180006ad7  push    rbp
0x180006ad9  sub     rsp, 20h
0x180006add  mov     rbp, rdx
0x180006ae0  mov     rax, [rcx]
0x180006ae3  mov     edx, [rax]
0x180006ae5  mov     [rbp+0B0h], rcx
0x180006aec  mov     [rbp+38h], edx
0x180006aef  mov     eax, [rbp+38h]
0x180006af2  cmp     eax, 0E06D7363h
0x180006af7  jnz     short loc_180006B0D
0x180006af9  mov     rdx, [rbp+0B0h]
0x180006b00  mov     ecx, [rbp+38h]
0x180006b03  call    _XcptFilter_0
0x180006b08  mov     [rbp+40h], eax
0x180006b0b  jmp     short loc_180006B14
0x180006b0d  mov     dword ptr [rbp+40h], 0
0x180006b14  mov     eax, [rbp+40h]
0x180006b17  add     rsp, 20h
0x180006b1b  pop     rbp
0x180006b1c  retn
0x180006b1e  push    rbp
0x180006b20  sub     rsp, 20h
0x180006b24  mov     rbp, rdx
0x180006b27  mov     rax, [rcx]
0x180006b2a  mov     edx, [rax]
0x180006b2c  mov     [rbp+0B8h], rcx
0x180006b33  mov     [rbp+48h], edx
0x180006b36  mov     eax, [rbp+48h]
0x180006b39  cmp     eax, 0E06D7363h
0x180006b3e  jnz     short loc_180006B54
0x180006b40  mov     rdx, [rbp+0B8h]
0x180006b47  mov     ecx, [rbp+48h]
0x180006b4a  call    _XcptFilter_0
0x180006b4f  mov     [rbp+50h], eax
0x180006b52  jmp     short loc_180006B5B
0x180006b54  mov     dword ptr [rbp+50h], 0
0x180006b5b  mov     eax, [rbp+50h]
0x180006b5e  add     rsp, 20h
0x180006b62  pop     rbp
0x180006b63  retn
0x180006b65  push    rbp
0x180006b67  sub     rsp, 20h
0x180006b6b  mov     rbp, rdx
0x180006b6e  mov     rax, [rcx]
0x180006b71  mov     edx, [rax]
0x180006b73  mov     [rbp+0C0h], rcx
0x180006b7a  mov     [rbp+58h], edx
0x180006b7d  mov     eax, [rbp+58h]
0x180006b80  cmp     eax, 0E06D7363h
0x180006b85  jnz     short loc_180006B9B
0x180006b87  mov     rdx, [rbp+0C0h]
0x180006b8e  mov     ecx, [rbp+58h]
0x180006b91  call    _XcptFilter_0
0x180006b96  mov     [rbp+60h], eax
0x180006b99  jmp     short loc_180006BA2
0x180006b9b  mov     dword ptr [rbp+60h], 0
0x180006ba2  mov     eax, [rbp+60h]
0x180006ba5  add     rsp, 20h
0x180006ba9  pop     rbp
0x180006baa  retn
0x180006bac  push    rbp
0x180006bae  sub     rsp, 20h
0x180006bb2  mov     rbp, rdx
0x180006bb5  mov     rax, [rcx]
0x180006bb8  mov     edx, [rax]
0x180006bba  mov     [rbp+0C8h], rcx
0x180006bc1  mov     [rbp+68h], edx
0x180006bc4  mov     eax, [rbp+68h]
0x180006bc7  cmp     eax, 0E06D7363h
0x180006bcc  jnz     short loc_180006BE2
0x180006bce  mov     rdx, [rbp+0C8h]
0x180006bd5  mov     ecx, [rbp+68h]
0x180006bd8  call    _XcptFilter_0
0x180006bdd  mov     [rbp+70h], eax
0x180006be0  jmp     short loc_180006BE9
0x180006be2  mov     dword ptr [rbp+70h], 0
0x180006be9  mov     eax, [rbp+70h]
0x180006bec  add     rsp, 20h
0x180006bf0  pop     rbp
0x180006bf1  retn
0x180006bf3  push    rbp
0x180006bf5  sub     rsp, 20h
0x180006bf9  mov     rbp, rdx
0x180006bfc  mov     rax, [rcx]
0x180006bff  mov     edx, [rax]
0x180006c01  mov     [rbp+0D0h], rcx
0x180006c08  mov     [rbp+78h], edx
0x180006c0b  mov     eax, [rbp+78h]
0x180006c0e  cmp     eax, 0E06D7363h
0x180006c13  jnz     short loc_180006C2C
0x180006c15  mov     rdx, [rbp+0D0h]
0x180006c1c  mov     ecx, [rbp+78h]
0x180006c1f  call    _XcptFilter_0
0x180006c24  mov     [rbp+80h], eax
0x180006c2a  jmp     short loc_180006C36
0x180006c2c  mov     dword ptr [rbp+80h], 0
0x180006c36  mov     eax, [rbp+80h]
0x180006c3c  add     rsp, 20h
0x180006c40  pop     rbp
0x180006c41  retn
0x180006c43  push    rbp
0x180006c45  sub     rsp, 20h
0x180006c49  mov     rbp, rdx
0x180006c4c  mov     rax, [rcx]
0x180006c4f  mov     edx, [rax]
0x180006c51  mov     [rbp+0D8h], rcx
0x180006c58  mov     [rbp+88h], edx
0x180006c5e  mov     eax, [rbp+88h]
0x180006c64  cmp     eax, 0E06D7363h
0x180006c69  jnz     short loc_180006C85
0x180006c6b  mov     rdx, [rbp+0D8h]
0x180006c72  mov     ecx, [rbp+88h]
0x180006c78  call    _XcptFilter_0
0x180006c7d  mov     [rbp+90h], eax
0x180006c83  jmp     short loc_180006C8F
0x180006c85  mov     dword ptr [rbp+90h], 0
0x180006c8f  mov     eax, [rbp+90h]
0x180006c95  add     rsp, 20h
0x180006c99  pop     rbp
0x180006c9a  retn
0x180006c9c  push    rbp
0x180006c9e  sub     rsp, 20h
0x180006ca2  mov     rbp, rdx
0x180006ca5  mov     rax, [rcx]
0x180006ca8  mov     edx, [rax]
0x180006caa  mov     [rbp+0E0h], rcx
0x180006cb1  mov     [rbp+98h], edx
0x180006cb7  mov     eax, [rbp+98h]
0x180006cbd  cmp     eax, 0E06D7363h
0x180006cc2  jnz     short loc_180006CDE
0x180006cc4  mov     rdx, [rbp+0E0h]
0x180006ccb  mov     ecx, [rbp+98h]
0x180006cd1  call    _XcptFilter_0
0x180006cd6  mov     [rbp+0A0h], eax
0x180006cdc  jmp     short loc_180006CE8
0x180006cde  mov     dword ptr [rbp+0A0h], 0
0x180006ce8  mov     eax, [rbp+0A0h]
0x180006cee  add     rsp, 20h
0x180006cf2  pop     rbp
0x180006cf3  retn
0x180006cf5  push    rbp
0x180006cf7  sub     rsp, 20h
0x180006cfb  mov     rbp, rdx
0x180006cfe  cmp     dword ptr [rbp+118h], 1
0x180006d05  ja      short loc_180006D11
0x180006d07  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
