# __DllMainCRTStartup

- ea: `0x180001664`
- end: `0x180001870`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001620`

## callees

- `0x1800013f0`
- `0x180001664`
- `0x180001d65`
- `0x180008b68`
- `0x1800128a0`

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
  if ( (_DWORD)fdwReason || dword_18001F368 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18001F36C = 1;
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
            if ( dword_18001F36C )
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
0x180001664  mov     [rsp+lpvReserved], r8
0x180001669  mov     [rsp+arg_8], edx
0x18000166d  mov     [rsp+arg_0], rcx
0x180001672  push    rbx
0x180001673  push    rsi
0x180001674  push    rdi
0x180001675  sub     rsp, 0F0h
0x18000167c  mov     edi, edx
0x18000167e  mov     rsi, rcx
0x180001681  mov     ebx, 1
0x180001686  cmp     edx, ebx
0x180001688  ja      short loc_180001690
0x18000168a  mov     cs:__native_dllmain_reason, edx
0x180001690  test    edx, edx
0x180001692  jnz     short loc_1800016A7
0x180001694  cmp     cs:dword_18001F368, edx
0x18000169a  jnz     short loc_1800016A7
0x18000169c  xor     ebx, ebx
0x18000169e  mov     [rsp+108h+var_E8], ebx
0x1800016a2  jmp     loc_180001854
0x1800016a7  lea     eax, [rdx-1]
0x1800016aa  cmp     eax, 1
0x1800016ad  ja      loc_180001734
0x1800016b3  mov     rax, cs:_pRawDllMain
0x1800016ba  test    rax, rax
0x1800016bd  jz      short loc_1800016F5
0x1800016bf  cmp     edx, 1
0x1800016c2  jnz     short loc_1800016CA
0x1800016c4  mov     cs:dword_18001F36C, edx
0x1800016ca  mov     r8, [rsp+108h+lpvReserved]
0x1800016d2  call    cs:__guard_dispatch_icall_fptr
0x1800016d8  mov     ebx, eax
0x1800016da  mov     [rsp+108h+var_E8], eax
0x1800016de  jmp     short loc_1800016F5
0x1800016e0  xor     ebx, ebx
0x1800016e2  mov     [rsp+108h+var_E8], ebx
0x1800016e6  mov     edi, [rsp+108h+arg_8]
0x1800016ed  mov     rsi, [rsp+108h+arg_0]
0x1800016f5  test    ebx, ebx
0x1800016f7  jz      loc_180001854
0x1800016fd  mov     r8, [rsp+108h+lpvReserved]
0x180001705  mov     edx, edi
0x180001707  mov     rcx, rsi
0x18000170a  call    _CRT_INIT
0x18000170f  mov     ebx, eax
0x180001711  mov     [rsp+108h+var_E8], eax
0x180001715  jmp     short loc_18000172C
0x180001717  xor     ebx, ebx
0x180001719  mov     [rsp+108h+var_E8], ebx
0x18000171d  mov     edi, [rsp+108h+arg_8]
0x180001724  mov     rsi, [rsp+108h+arg_0]
0x18000172c  test    ebx, ebx
0x18000172e  jz      loc_180001854
0x180001734  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000173c  mov     edx, edi; fdwReason
0x18000173e  mov     rcx, rsi; hinstDLL
0x180001741  call    DllMain
0x180001746  mov     ebx, eax
0x180001748  mov     [rsp+108h+var_E8], eax
0x18000174c  jmp     short loc_180001763
0x18000174e  xor     ebx, ebx
0x180001750  mov     [rsp+108h+var_E8], ebx
0x180001754  mov     edi, [rsp+108h+arg_8]
0x18000175b  mov     rsi, [rsp+108h+arg_0]
0x180001763  cmp     edi, 1
0x180001766  jnz     short loc_1800017DF
0x180001768  test    ebx, ebx
0x18000176a  jnz     short loc_1800017DF
0x18000176c  xor     r8d, r8d; lpvReserved
0x18000176f  xor     edx, edx; fdwReason
0x180001771  mov     rcx, rsi; hinstDLL
0x180001774  call    DllMain
0x180001779  jmp     short loc_18000178E
0x18000177b  mov     edi, [rsp+108h+arg_8]
0x180001782  mov     rsi, [rsp+108h+arg_0]
0x18000178a  mov     ebx, [rsp+108h+var_E8]
0x18000178e  xor     r8d, r8d
0x180001791  xor     edx, edx
0x180001793  mov     rcx, rsi
0x180001796  call    _CRT_INIT
0x18000179b  jmp     short loc_1800017B0
0x18000179d  mov     edi, [rsp+108h+arg_8]
0x1800017a4  mov     rsi, [rsp+108h+arg_0]
0x1800017ac  mov     ebx, [rsp+108h+var_E8]
0x1800017b0  mov     rax, cs:_pRawDllMain
0x1800017b7  test    rax, rax
0x1800017ba  jz      short loc_1800017DF
0x1800017bc  xor     r8d, r8d
0x1800017bf  xor     edx, edx
0x1800017c1  mov     rcx, rsi
0x1800017c4  call    cs:__guard_dispatch_icall_fptr
0x1800017ca  jmp     short loc_1800017DF
0x1800017cc  mov     edi, [rsp+108h+arg_8]
0x1800017d3  mov     rsi, [rsp+108h+arg_0]
0x1800017db  mov     ebx, [rsp+108h+var_E8]
0x1800017df  test    edi, edi
0x1800017e1  jz      short loc_1800017E8
0x1800017e3  cmp     edi, 3
0x1800017e6  jnz     short loc_180001854
0x1800017e8  mov     r8, [rsp+108h+lpvReserved]
0x1800017f0  mov     edx, edi
0x1800017f2  mov     rcx, rsi
0x1800017f5  call    _CRT_INIT
0x1800017fa  mov     ebx, eax
0x1800017fc  mov     [rsp+108h+var_E8], eax
0x180001800  jmp     short loc_180001817
0x180001802  xor     ebx, ebx
0x180001804  mov     [rsp+108h+var_E8], ebx
0x180001808  mov     edi, [rsp+108h+arg_8]
0x18000180f  mov     rsi, [rsp+108h+arg_0]
0x180001817  mov     rax, cs:_pRawDllMain
0x18000181e  test    rax, rax
0x180001821  jz      short loc_180001854
0x180001823  cmp     cs:dword_18001F36C, 0
0x18000182a  jz      short loc_180001854
0x18000182c  mov     r8, [rsp+108h+lpvReserved]
0x180001834  mov     edx, edi
0x180001836  mov     rcx, rsi
0x180001839  call    cs:__guard_dispatch_icall_fptr
0x18000183f  mov     ebx, eax
0x180001841  mov     [rsp+108h+var_E8], eax
0x180001845  jmp     short loc_180001854
0x180001847  xor     ebx, ebx
0x180001849  mov     [rsp+108h+var_E8], ebx
0x18000184d  mov     edi, [rsp+108h+arg_8]
0x180001854  cmp     edi, 1
0x180001857  ja      short loc_180001863
0x180001859  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001863  mov     eax, ebx
0x180001865  add     rsp, 0F0h
0x18000186c  pop     rdi
0x18000186d  pop     rsi
0x18000186e  pop     rbx
0x18000186f  retn
0x180012943  push    rbp
0x180012945  sub     rsp, 20h
0x180012949  mov     rbp, rdx
0x18001294c  mov     rax, [rcx]
0x18001294f  mov     edx, [rax]
0x180012951  mov     [rbp+0A8h], rcx
0x180012958  mov     [rbp+28h], edx
0x18001295b  mov     eax, [rbp+28h]
0x18001295e  cmp     eax, 0E06D7363h
0x180012963  jnz     short loc_180012979
0x180012965  mov     rdx, [rbp+0A8h]
0x18001296c  mov     ecx, [rbp+28h]
0x18001296f  call    _XcptFilter_0
0x180012974  mov     [rbp+30h], eax
0x180012977  jmp     short loc_180012980
0x180012979  mov     dword ptr [rbp+30h], 0
0x180012980  mov     eax, [rbp+30h]
0x180012983  add     rsp, 20h
0x180012987  pop     rbp
0x180012988  retn
0x18001298a  push    rbp
0x18001298c  sub     rsp, 20h
0x180012990  mov     rbp, rdx
0x180012993  mov     rax, [rcx]
0x180012996  mov     edx, [rax]
0x180012998  mov     [rbp+0B0h], rcx
0x18001299f  mov     [rbp+38h], edx
0x1800129a2  mov     eax, [rbp+38h]
0x1800129a5  cmp     eax, 0E06D7363h
0x1800129aa  jnz     short loc_1800129C0
0x1800129ac  mov     rdx, [rbp+0B0h]
0x1800129b3  mov     ecx, [rbp+38h]
0x1800129b6  call    _XcptFilter_0
0x1800129bb  mov     [rbp+40h], eax
0x1800129be  jmp     short loc_1800129C7
0x1800129c0  mov     dword ptr [rbp+40h], 0
0x1800129c7  mov     eax, [rbp+40h]
0x1800129ca  add     rsp, 20h
0x1800129ce  pop     rbp
0x1800129cf  retn
0x1800129d1  push    rbp
0x1800129d3  sub     rsp, 20h
0x1800129d7  mov     rbp, rdx
0x1800129da  mov     rax, [rcx]
0x1800129dd  mov     edx, [rax]
0x1800129df  mov     [rbp+0B8h], rcx
0x1800129e6  mov     [rbp+48h], edx
0x1800129e9  mov     eax, [rbp+48h]
0x1800129ec  cmp     eax, 0E06D7363h
0x1800129f1  jnz     short loc_180012A07
0x1800129f3  mov     rdx, [rbp+0B8h]
0x1800129fa  mov     ecx, [rbp+48h]
0x1800129fd  call    _XcptFilter_0
0x180012a02  mov     [rbp+50h], eax
0x180012a05  jmp     short loc_180012A0E
0x180012a07  mov     dword ptr [rbp+50h], 0
0x180012a0e  mov     eax, [rbp+50h]
0x180012a11  add     rsp, 20h
0x180012a15  pop     rbp
0x180012a16  retn
0x180012a18  push    rbp
0x180012a1a  sub     rsp, 20h
0x180012a1e  mov     rbp, rdx
0x180012a21  mov     rax, [rcx]
0x180012a24  mov     edx, [rax]
0x180012a26  mov     [rbp+0C0h], rcx
0x180012a2d  mov     [rbp+58h], edx
0x180012a30  mov     eax, [rbp+58h]
0x180012a33  cmp     eax, 0E06D7363h
0x180012a38  jnz     short loc_180012A4E
0x180012a3a  mov     rdx, [rbp+0C0h]
0x180012a41  mov     ecx, [rbp+58h]
0x180012a44  call    _XcptFilter_0
0x180012a49  mov     [rbp+60h], eax
0x180012a4c  jmp     short loc_180012A55
0x180012a4e  mov     dword ptr [rbp+60h], 0
0x180012a55  mov     eax, [rbp+60h]
0x180012a58  add     rsp, 20h
0x180012a5c  pop     rbp
0x180012a5d  retn
0x180012a5f  push    rbp
0x180012a61  sub     rsp, 20h
0x180012a65  mov     rbp, rdx
0x180012a68  mov     rax, [rcx]
0x180012a6b  mov     edx, [rax]
0x180012a6d  mov     [rbp+0C8h], rcx
0x180012a74  mov     [rbp+68h], edx
0x180012a77  mov     eax, [rbp+68h]
0x180012a7a  cmp     eax, 0E06D7363h
0x180012a7f  jnz     short loc_180012A95
0x180012a81  mov     rdx, [rbp+0C8h]
0x180012a88  mov     ecx, [rbp+68h]
0x180012a8b  call    _XcptFilter_0
0x180012a90  mov     [rbp+70h], eax
0x180012a93  jmp     short loc_180012A9C
0x180012a95  mov     dword ptr [rbp+70h], 0
0x180012a9c  mov     eax, [rbp+70h]
0x180012a9f  add     rsp, 20h
0x180012aa3  pop     rbp
0x180012aa4  retn
0x180012aa6  push    rbp
0x180012aa8  sub     rsp, 20h
0x180012aac  mov     rbp, rdx
0x180012aaf  mov     rax, [rcx]
0x180012ab2  mov     edx, [rax]
0x180012ab4  mov     [rbp+0D0h], rcx
0x180012abb  mov     [rbp+78h], edx
0x180012abe  mov     eax, [rbp+78h]
0x180012ac1  cmp     eax, 0E06D7363h
0x180012ac6  jnz     short loc_180012ADF
0x180012ac8  mov     rdx, [rbp+0D0h]
0x180012acf  mov     ecx, [rbp+78h]
0x180012ad2  call    _XcptFilter_0
0x180012ad7  mov     [rbp+80h], eax
0x180012add  jmp     short loc_180012AE9
0x180012adf  mov     dword ptr [rbp+80h], 0
0x180012ae9  mov     eax, [rbp+80h]
0x180012aef  add     rsp, 20h
0x180012af3  pop     rbp
0x180012af4  retn
0x180012af6  push    rbp
0x180012af8  sub     rsp, 20h
0x180012afc  mov     rbp, rdx
0x180012aff  mov     rax, [rcx]
0x180012b02  mov     edx, [rax]
0x180012b04  mov     [rbp+0D8h], rcx
0x180012b0b  mov     [rbp+88h], edx
0x180012b11  mov     eax, [rbp+88h]
0x180012b17  cmp     eax, 0E06D7363h
0x180012b1c  jnz     short loc_180012B38
0x180012b1e  mov     rdx, [rbp+0D8h]
0x180012b25  mov     ecx, [rbp+88h]
0x180012b2b  call    _XcptFilter_0
0x180012b30  mov     [rbp+90h], eax
0x180012b36  jmp     short loc_180012B42
0x180012b38  mov     dword ptr [rbp+90h], 0
0x180012b42  mov     eax, [rbp+90h]
0x180012b48  add     rsp, 20h
0x180012b4c  pop     rbp
0x180012b4d  retn
0x180012b4f  push    rbp
0x180012b51  sub     rsp, 20h
0x180012b55  mov     rbp, rdx
0x180012b58  mov     rax, [rcx]
0x180012b5b  mov     edx, [rax]
0x180012b5d  mov     [rbp+0E0h], rcx
0x180012b64  mov     [rbp+98h], edx
0x180012b6a  mov     eax, [rbp+98h]
0x180012b70  cmp     eax, 0E06D7363h
0x180012b75  jnz     short loc_180012B91
0x180012b77  mov     rdx, [rbp+0E0h]
0x180012b7e  mov     ecx, [rbp+98h]
0x180012b84  call    _XcptFilter_0
0x180012b89  mov     [rbp+0A0h], eax
0x180012b8f  jmp     short loc_180012B9B
0x180012b91  mov     dword ptr [rbp+0A0h], 0
0x180012b9b  mov     eax, [rbp+0A0h]
0x180012ba1  add     rsp, 20h
0x180012ba5  pop     rbp
0x180012ba6  retn
0x180012ba8  push    rbp
0x180012baa  sub     rsp, 20h
0x180012bae  mov     rbp, rdx
0x180012bb1  cmp     dword ptr [rbp+118h], 1
0x180012bb8  ja      short loc_180012BC4
0x180012bba  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
