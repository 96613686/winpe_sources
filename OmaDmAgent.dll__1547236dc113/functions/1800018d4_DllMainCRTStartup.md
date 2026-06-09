# __DllMainCRTStartup

- ea: `0x1800018d4`
- end: `0x180001ae0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001890`

## callees

- `0x180001660`
- `0x1800018d4`
- `0x180001c3e`
- `0x180002184`
- `0x18001f490`

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
  if ( (_DWORD)fdwReason || dword_18002B204 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18002B208 = 1;
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
            if ( dword_18002B208 )
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
0x1800018d4  mov     [rsp+lpvReserved], r8
0x1800018d9  mov     [rsp+arg_8], edx
0x1800018dd  mov     [rsp+arg_0], rcx
0x1800018e2  push    rbx
0x1800018e3  push    rsi
0x1800018e4  push    rdi
0x1800018e5  sub     rsp, 0F0h
0x1800018ec  mov     edi, edx
0x1800018ee  mov     rsi, rcx
0x1800018f1  mov     ebx, 1
0x1800018f6  cmp     edx, ebx
0x1800018f8  ja      short loc_180001900
0x1800018fa  mov     cs:__native_dllmain_reason, edx
0x180001900  test    edx, edx
0x180001902  jnz     short loc_180001917
0x180001904  cmp     cs:dword_18002B204, edx
0x18000190a  jnz     short loc_180001917
0x18000190c  xor     ebx, ebx
0x18000190e  mov     [rsp+108h+var_E8], ebx
0x180001912  jmp     loc_180001AC4
0x180001917  lea     eax, [rdx-1]
0x18000191a  cmp     eax, 1
0x18000191d  ja      loc_1800019A4
0x180001923  mov     rax, cs:_pRawDllMain
0x18000192a  test    rax, rax
0x18000192d  jz      short loc_180001965
0x18000192f  cmp     edx, 1
0x180001932  jnz     short loc_18000193A
0x180001934  mov     cs:dword_18002B208, edx
0x18000193a  mov     r8, [rsp+108h+lpvReserved]
0x180001942  call    cs:__guard_dispatch_icall_fptr
0x180001948  mov     ebx, eax
0x18000194a  mov     [rsp+108h+var_E8], eax
0x18000194e  jmp     short loc_180001965
0x180001950  xor     ebx, ebx
0x180001952  mov     [rsp+108h+var_E8], ebx
0x180001956  mov     edi, [rsp+108h+arg_8]
0x18000195d  mov     rsi, [rsp+108h+arg_0]
0x180001965  test    ebx, ebx
0x180001967  jz      loc_180001AC4
0x18000196d  mov     r8, [rsp+108h+lpvReserved]
0x180001975  mov     edx, edi
0x180001977  mov     rcx, rsi
0x18000197a  call    _CRT_INIT
0x18000197f  mov     ebx, eax
0x180001981  mov     [rsp+108h+var_E8], eax
0x180001985  jmp     short loc_18000199C
0x180001987  xor     ebx, ebx
0x180001989  mov     [rsp+108h+var_E8], ebx
0x18000198d  mov     edi, [rsp+108h+arg_8]
0x180001994  mov     rsi, [rsp+108h+arg_0]
0x18000199c  test    ebx, ebx
0x18000199e  jz      loc_180001AC4
0x1800019a4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800019ac  mov     edx, edi; fdwReason
0x1800019ae  mov     rcx, rsi; hinstDLL
0x1800019b1  call    DllMain
0x1800019b6  mov     ebx, eax
0x1800019b8  mov     [rsp+108h+var_E8], eax
0x1800019bc  jmp     short loc_1800019D3
0x1800019be  xor     ebx, ebx
0x1800019c0  mov     [rsp+108h+var_E8], ebx
0x1800019c4  mov     edi, [rsp+108h+arg_8]
0x1800019cb  mov     rsi, [rsp+108h+arg_0]
0x1800019d3  cmp     edi, 1
0x1800019d6  jnz     short loc_180001A4F
0x1800019d8  test    ebx, ebx
0x1800019da  jnz     short loc_180001A4F
0x1800019dc  xor     r8d, r8d; lpvReserved
0x1800019df  xor     edx, edx; fdwReason
0x1800019e1  mov     rcx, rsi; hinstDLL
0x1800019e4  call    DllMain
0x1800019e9  jmp     short loc_1800019FE
0x1800019eb  mov     edi, [rsp+108h+arg_8]
0x1800019f2  mov     rsi, [rsp+108h+arg_0]
0x1800019fa  mov     ebx, [rsp+108h+var_E8]
0x1800019fe  xor     r8d, r8d
0x180001a01  xor     edx, edx
0x180001a03  mov     rcx, rsi
0x180001a06  call    _CRT_INIT
0x180001a0b  jmp     short loc_180001A20
0x180001a0d  mov     edi, [rsp+108h+arg_8]
0x180001a14  mov     rsi, [rsp+108h+arg_0]
0x180001a1c  mov     ebx, [rsp+108h+var_E8]
0x180001a20  mov     rax, cs:_pRawDllMain
0x180001a27  test    rax, rax
0x180001a2a  jz      short loc_180001A4F
0x180001a2c  xor     r8d, r8d
0x180001a2f  xor     edx, edx
0x180001a31  mov     rcx, rsi
0x180001a34  call    cs:__guard_dispatch_icall_fptr
0x180001a3a  jmp     short loc_180001A4F
0x180001a3c  mov     edi, [rsp+108h+arg_8]
0x180001a43  mov     rsi, [rsp+108h+arg_0]
0x180001a4b  mov     ebx, [rsp+108h+var_E8]
0x180001a4f  test    edi, edi
0x180001a51  jz      short loc_180001A58
0x180001a53  cmp     edi, 3
0x180001a56  jnz     short loc_180001AC4
0x180001a58  mov     r8, [rsp+108h+lpvReserved]
0x180001a60  mov     edx, edi
0x180001a62  mov     rcx, rsi
0x180001a65  call    _CRT_INIT
0x180001a6a  mov     ebx, eax
0x180001a6c  mov     [rsp+108h+var_E8], eax
0x180001a70  jmp     short loc_180001A87
0x180001a72  xor     ebx, ebx
0x180001a74  mov     [rsp+108h+var_E8], ebx
0x180001a78  mov     edi, [rsp+108h+arg_8]
0x180001a7f  mov     rsi, [rsp+108h+arg_0]
0x180001a87  mov     rax, cs:_pRawDllMain
0x180001a8e  test    rax, rax
0x180001a91  jz      short loc_180001AC4
0x180001a93  cmp     cs:dword_18002B208, 0
0x180001a9a  jz      short loc_180001AC4
0x180001a9c  mov     r8, [rsp+108h+lpvReserved]
0x180001aa4  mov     edx, edi
0x180001aa6  mov     rcx, rsi
0x180001aa9  call    cs:__guard_dispatch_icall_fptr
0x180001aaf  mov     ebx, eax
0x180001ab1  mov     [rsp+108h+var_E8], eax
0x180001ab5  jmp     short loc_180001AC4
0x180001ab7  xor     ebx, ebx
0x180001ab9  mov     [rsp+108h+var_E8], ebx
0x180001abd  mov     edi, [rsp+108h+arg_8]
0x180001ac4  cmp     edi, 1
0x180001ac7  ja      short loc_180001AD3
0x180001ac9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001ad3  mov     eax, ebx
0x180001ad5  add     rsp, 0F0h
0x180001adc  pop     rdi
0x180001add  pop     rsi
0x180001ade  pop     rbx
0x180001adf  retn
0x18001f533  push    rbp
0x18001f535  sub     rsp, 20h
0x18001f539  mov     rbp, rdx
0x18001f53c  mov     rax, [rcx]
0x18001f53f  mov     edx, [rax]
0x18001f541  mov     [rbp+0A8h], rcx
0x18001f548  mov     [rbp+28h], edx
0x18001f54b  mov     eax, [rbp+28h]
0x18001f54e  cmp     eax, 0E06D7363h
0x18001f553  jnz     short loc_18001F569
0x18001f555  mov     rdx, [rbp+0A8h]
0x18001f55c  mov     ecx, [rbp+28h]
0x18001f55f  call    _XcptFilter_0
0x18001f564  mov     [rbp+30h], eax
0x18001f567  jmp     short loc_18001F570
0x18001f569  mov     dword ptr [rbp+30h], 0
0x18001f570  mov     eax, [rbp+30h]
0x18001f573  add     rsp, 20h
0x18001f577  pop     rbp
0x18001f578  retn
0x18001f57a  push    rbp
0x18001f57c  sub     rsp, 20h
0x18001f580  mov     rbp, rdx
0x18001f583  mov     rax, [rcx]
0x18001f586  mov     edx, [rax]
0x18001f588  mov     [rbp+0B0h], rcx
0x18001f58f  mov     [rbp+38h], edx
0x18001f592  mov     eax, [rbp+38h]
0x18001f595  cmp     eax, 0E06D7363h
0x18001f59a  jnz     short loc_18001F5B0
0x18001f59c  mov     rdx, [rbp+0B0h]
0x18001f5a3  mov     ecx, [rbp+38h]
0x18001f5a6  call    _XcptFilter_0
0x18001f5ab  mov     [rbp+40h], eax
0x18001f5ae  jmp     short loc_18001F5B7
0x18001f5b0  mov     dword ptr [rbp+40h], 0
0x18001f5b7  mov     eax, [rbp+40h]
0x18001f5ba  add     rsp, 20h
0x18001f5be  pop     rbp
0x18001f5bf  retn
0x18001f5c1  push    rbp
0x18001f5c3  sub     rsp, 20h
0x18001f5c7  mov     rbp, rdx
0x18001f5ca  mov     rax, [rcx]
0x18001f5cd  mov     edx, [rax]
0x18001f5cf  mov     [rbp+0B8h], rcx
0x18001f5d6  mov     [rbp+48h], edx
0x18001f5d9  mov     eax, [rbp+48h]
0x18001f5dc  cmp     eax, 0E06D7363h
0x18001f5e1  jnz     short loc_18001F5F7
0x18001f5e3  mov     rdx, [rbp+0B8h]
0x18001f5ea  mov     ecx, [rbp+48h]
0x18001f5ed  call    _XcptFilter_0
0x18001f5f2  mov     [rbp+50h], eax
0x18001f5f5  jmp     short loc_18001F5FE
0x18001f5f7  mov     dword ptr [rbp+50h], 0
0x18001f5fe  mov     eax, [rbp+50h]
0x18001f601  add     rsp, 20h
0x18001f605  pop     rbp
0x18001f606  retn
0x18001f608  push    rbp
0x18001f60a  sub     rsp, 20h
0x18001f60e  mov     rbp, rdx
0x18001f611  mov     rax, [rcx]
0x18001f614  mov     edx, [rax]
0x18001f616  mov     [rbp+0C0h], rcx
0x18001f61d  mov     [rbp+58h], edx
0x18001f620  mov     eax, [rbp+58h]
0x18001f623  cmp     eax, 0E06D7363h
0x18001f628  jnz     short loc_18001F63E
0x18001f62a  mov     rdx, [rbp+0C0h]
0x18001f631  mov     ecx, [rbp+58h]
0x18001f634  call    _XcptFilter_0
0x18001f639  mov     [rbp+60h], eax
0x18001f63c  jmp     short loc_18001F645
0x18001f63e  mov     dword ptr [rbp+60h], 0
0x18001f645  mov     eax, [rbp+60h]
0x18001f648  add     rsp, 20h
0x18001f64c  pop     rbp
0x18001f64d  retn
0x18001f64f  push    rbp
0x18001f651  sub     rsp, 20h
0x18001f655  mov     rbp, rdx
0x18001f658  mov     rax, [rcx]
0x18001f65b  mov     edx, [rax]
0x18001f65d  mov     [rbp+0C8h], rcx
0x18001f664  mov     [rbp+68h], edx
0x18001f667  mov     eax, [rbp+68h]
0x18001f66a  cmp     eax, 0E06D7363h
0x18001f66f  jnz     short loc_18001F685
0x18001f671  mov     rdx, [rbp+0C8h]
0x18001f678  mov     ecx, [rbp+68h]
0x18001f67b  call    _XcptFilter_0
0x18001f680  mov     [rbp+70h], eax
0x18001f683  jmp     short loc_18001F68C
0x18001f685  mov     dword ptr [rbp+70h], 0
0x18001f68c  mov     eax, [rbp+70h]
0x18001f68f  add     rsp, 20h
0x18001f693  pop     rbp
0x18001f694  retn
0x18001f696  push    rbp
0x18001f698  sub     rsp, 20h
0x18001f69c  mov     rbp, rdx
0x18001f69f  mov     rax, [rcx]
0x18001f6a2  mov     edx, [rax]
0x18001f6a4  mov     [rbp+0D0h], rcx
0x18001f6ab  mov     [rbp+78h], edx
0x18001f6ae  mov     eax, [rbp+78h]
0x18001f6b1  cmp     eax, 0E06D7363h
0x18001f6b6  jnz     short loc_18001F6CF
0x18001f6b8  mov     rdx, [rbp+0D0h]
0x18001f6bf  mov     ecx, [rbp+78h]
0x18001f6c2  call    _XcptFilter_0
0x18001f6c7  mov     [rbp+80h], eax
0x18001f6cd  jmp     short loc_18001F6D9
0x18001f6cf  mov     dword ptr [rbp+80h], 0
0x18001f6d9  mov     eax, [rbp+80h]
0x18001f6df  add     rsp, 20h
0x18001f6e3  pop     rbp
0x18001f6e4  retn
0x18001f6e6  push    rbp
0x18001f6e8  sub     rsp, 20h
0x18001f6ec  mov     rbp, rdx
0x18001f6ef  mov     rax, [rcx]
0x18001f6f2  mov     edx, [rax]
0x18001f6f4  mov     [rbp+0D8h], rcx
0x18001f6fb  mov     [rbp+88h], edx
0x18001f701  mov     eax, [rbp+88h]
0x18001f707  cmp     eax, 0E06D7363h
0x18001f70c  jnz     short loc_18001F728
0x18001f70e  mov     rdx, [rbp+0D8h]
0x18001f715  mov     ecx, [rbp+88h]
0x18001f71b  call    _XcptFilter_0
0x18001f720  mov     [rbp+90h], eax
0x18001f726  jmp     short loc_18001F732
0x18001f728  mov     dword ptr [rbp+90h], 0
0x18001f732  mov     eax, [rbp+90h]
0x18001f738  add     rsp, 20h
0x18001f73c  pop     rbp
0x18001f73d  retn
0x18001f73f  push    rbp
0x18001f741  sub     rsp, 20h
0x18001f745  mov     rbp, rdx
0x18001f748  mov     rax, [rcx]
0x18001f74b  mov     edx, [rax]
0x18001f74d  mov     [rbp+0E0h], rcx
0x18001f754  mov     [rbp+98h], edx
0x18001f75a  mov     eax, [rbp+98h]
0x18001f760  cmp     eax, 0E06D7363h
0x18001f765  jnz     short loc_18001F781
0x18001f767  mov     rdx, [rbp+0E0h]
0x18001f76e  mov     ecx, [rbp+98h]
0x18001f774  call    _XcptFilter_0
0x18001f779  mov     [rbp+0A0h], eax
0x18001f77f  jmp     short loc_18001F78B
0x18001f781  mov     dword ptr [rbp+0A0h], 0
0x18001f78b  mov     eax, [rbp+0A0h]
0x18001f791  add     rsp, 20h
0x18001f795  pop     rbp
0x18001f796  retn
0x18001f798  push    rbp
0x18001f79a  sub     rsp, 20h
0x18001f79e  mov     rbp, rdx
0x18001f7a1  cmp     dword ptr [rbp+118h], 1
0x18001f7a8  ja      short loc_18001F7B4
0x18001f7aa  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
