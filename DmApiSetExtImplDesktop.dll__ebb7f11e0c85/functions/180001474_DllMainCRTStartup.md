# __DllMainCRTStartup

- ea: `0x180001474`
- end: `0x180001680`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001430`

## callees

- `0x180001200`
- `0x180001474`
- `0x1800019db`
- `0x180001bb8`
- `0x180009f70`

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
  if ( (_DWORD)fdwReason || dword_180012244 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180012248 = 1;
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
            if ( dword_180012248 )
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
0x180001474  mov     [rsp+lpvReserved], r8
0x180001479  mov     [rsp+arg_8], edx
0x18000147d  mov     [rsp+arg_0], rcx
0x180001482  push    rbx
0x180001483  push    rsi
0x180001484  push    rdi
0x180001485  sub     rsp, 0F0h
0x18000148c  mov     edi, edx
0x18000148e  mov     rsi, rcx
0x180001491  mov     ebx, 1
0x180001496  cmp     edx, ebx
0x180001498  ja      short loc_1800014A0
0x18000149a  mov     cs:__native_dllmain_reason, edx
0x1800014a0  test    edx, edx
0x1800014a2  jnz     short loc_1800014B7
0x1800014a4  cmp     cs:dword_180012244, edx
0x1800014aa  jnz     short loc_1800014B7
0x1800014ac  xor     ebx, ebx
0x1800014ae  mov     [rsp+108h+var_E8], ebx
0x1800014b2  jmp     loc_180001664
0x1800014b7  lea     eax, [rdx-1]
0x1800014ba  cmp     eax, 1
0x1800014bd  ja      loc_180001544
0x1800014c3  mov     rax, cs:_pRawDllMain
0x1800014ca  test    rax, rax
0x1800014cd  jz      short loc_180001505
0x1800014cf  cmp     edx, 1
0x1800014d2  jnz     short loc_1800014DA
0x1800014d4  mov     cs:dword_180012248, edx
0x1800014da  mov     r8, [rsp+108h+lpvReserved]
0x1800014e2  call    cs:__guard_dispatch_icall_fptr
0x1800014e8  mov     ebx, eax
0x1800014ea  mov     [rsp+108h+var_E8], eax
0x1800014ee  jmp     short loc_180001505
0x1800014f0  xor     ebx, ebx
0x1800014f2  mov     [rsp+108h+var_E8], ebx
0x1800014f6  mov     edi, [rsp+108h+arg_8]
0x1800014fd  mov     rsi, [rsp+108h+arg_0]
0x180001505  test    ebx, ebx
0x180001507  jz      loc_180001664
0x18000150d  mov     r8, [rsp+108h+lpvReserved]
0x180001515  mov     edx, edi
0x180001517  mov     rcx, rsi
0x18000151a  call    _CRT_INIT
0x18000151f  mov     ebx, eax
0x180001521  mov     [rsp+108h+var_E8], eax
0x180001525  jmp     short loc_18000153C
0x180001527  xor     ebx, ebx
0x180001529  mov     [rsp+108h+var_E8], ebx
0x18000152d  mov     edi, [rsp+108h+arg_8]
0x180001534  mov     rsi, [rsp+108h+arg_0]
0x18000153c  test    ebx, ebx
0x18000153e  jz      loc_180001664
0x180001544  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000154c  mov     edx, edi; fdwReason
0x18000154e  mov     rcx, rsi; hinstDLL
0x180001551  call    DllMain
0x180001556  mov     ebx, eax
0x180001558  mov     [rsp+108h+var_E8], eax
0x18000155c  jmp     short loc_180001573
0x18000155e  xor     ebx, ebx
0x180001560  mov     [rsp+108h+var_E8], ebx
0x180001564  mov     edi, [rsp+108h+arg_8]
0x18000156b  mov     rsi, [rsp+108h+arg_0]
0x180001573  cmp     edi, 1
0x180001576  jnz     short loc_1800015EF
0x180001578  test    ebx, ebx
0x18000157a  jnz     short loc_1800015EF
0x18000157c  xor     r8d, r8d; lpvReserved
0x18000157f  xor     edx, edx; fdwReason
0x180001581  mov     rcx, rsi; hinstDLL
0x180001584  call    DllMain
0x180001589  jmp     short loc_18000159E
0x18000158b  mov     edi, [rsp+108h+arg_8]
0x180001592  mov     rsi, [rsp+108h+arg_0]
0x18000159a  mov     ebx, [rsp+108h+var_E8]
0x18000159e  xor     r8d, r8d
0x1800015a1  xor     edx, edx
0x1800015a3  mov     rcx, rsi
0x1800015a6  call    _CRT_INIT
0x1800015ab  jmp     short loc_1800015C0
0x1800015ad  mov     edi, [rsp+108h+arg_8]
0x1800015b4  mov     rsi, [rsp+108h+arg_0]
0x1800015bc  mov     ebx, [rsp+108h+var_E8]
0x1800015c0  mov     rax, cs:_pRawDllMain
0x1800015c7  test    rax, rax
0x1800015ca  jz      short loc_1800015EF
0x1800015cc  xor     r8d, r8d
0x1800015cf  xor     edx, edx
0x1800015d1  mov     rcx, rsi
0x1800015d4  call    cs:__guard_dispatch_icall_fptr
0x1800015da  jmp     short loc_1800015EF
0x1800015dc  mov     edi, [rsp+108h+arg_8]
0x1800015e3  mov     rsi, [rsp+108h+arg_0]
0x1800015eb  mov     ebx, [rsp+108h+var_E8]
0x1800015ef  test    edi, edi
0x1800015f1  jz      short loc_1800015F8
0x1800015f3  cmp     edi, 3
0x1800015f6  jnz     short loc_180001664
0x1800015f8  mov     r8, [rsp+108h+lpvReserved]
0x180001600  mov     edx, edi
0x180001602  mov     rcx, rsi
0x180001605  call    _CRT_INIT
0x18000160a  mov     ebx, eax
0x18000160c  mov     [rsp+108h+var_E8], eax
0x180001610  jmp     short loc_180001627
0x180001612  xor     ebx, ebx
0x180001614  mov     [rsp+108h+var_E8], ebx
0x180001618  mov     edi, [rsp+108h+arg_8]
0x18000161f  mov     rsi, [rsp+108h+arg_0]
0x180001627  mov     rax, cs:_pRawDllMain
0x18000162e  test    rax, rax
0x180001631  jz      short loc_180001664
0x180001633  cmp     cs:dword_180012248, 0
0x18000163a  jz      short loc_180001664
0x18000163c  mov     r8, [rsp+108h+lpvReserved]
0x180001644  mov     edx, edi
0x180001646  mov     rcx, rsi
0x180001649  call    cs:__guard_dispatch_icall_fptr
0x18000164f  mov     ebx, eax
0x180001651  mov     [rsp+108h+var_E8], eax
0x180001655  jmp     short loc_180001664
0x180001657  xor     ebx, ebx
0x180001659  mov     [rsp+108h+var_E8], ebx
0x18000165d  mov     edi, [rsp+108h+arg_8]
0x180001664  cmp     edi, 1
0x180001667  ja      short loc_180001673
0x180001669  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001673  mov     eax, ebx
0x180001675  add     rsp, 0F0h
0x18000167c  pop     rdi
0x18000167d  pop     rsi
0x18000167e  pop     rbx
0x18000167f  retn
0x18000a043  push    rbp
0x18000a045  sub     rsp, 20h
0x18000a049  mov     rbp, rdx
0x18000a04c  mov     rax, [rcx]
0x18000a04f  mov     edx, [rax]
0x18000a051  mov     [rbp+0A8h], rcx
0x18000a058  mov     [rbp+28h], edx
0x18000a05b  mov     eax, [rbp+28h]
0x18000a05e  cmp     eax, 0E06D7363h
0x18000a063  jnz     short loc_18000A079
0x18000a065  mov     rdx, [rbp+0A8h]
0x18000a06c  mov     ecx, [rbp+28h]
0x18000a06f  call    _XcptFilter_0
0x18000a074  mov     [rbp+30h], eax
0x18000a077  jmp     short loc_18000A080
0x18000a079  mov     dword ptr [rbp+30h], 0
0x18000a080  mov     eax, [rbp+30h]
0x18000a083  add     rsp, 20h
0x18000a087  pop     rbp
0x18000a088  retn
0x18000a08a  push    rbp
0x18000a08c  sub     rsp, 20h
0x18000a090  mov     rbp, rdx
0x18000a093  mov     rax, [rcx]
0x18000a096  mov     edx, [rax]
0x18000a098  mov     [rbp+0B0h], rcx
0x18000a09f  mov     [rbp+38h], edx
0x18000a0a2  mov     eax, [rbp+38h]
0x18000a0a5  cmp     eax, 0E06D7363h
0x18000a0aa  jnz     short loc_18000A0C0
0x18000a0ac  mov     rdx, [rbp+0B0h]
0x18000a0b3  mov     ecx, [rbp+38h]
0x18000a0b6  call    _XcptFilter_0
0x18000a0bb  mov     [rbp+40h], eax
0x18000a0be  jmp     short loc_18000A0C7
0x18000a0c0  mov     dword ptr [rbp+40h], 0
0x18000a0c7  mov     eax, [rbp+40h]
0x18000a0ca  add     rsp, 20h
0x18000a0ce  pop     rbp
0x18000a0cf  retn
0x18000a0d1  push    rbp
0x18000a0d3  sub     rsp, 20h
0x18000a0d7  mov     rbp, rdx
0x18000a0da  mov     rax, [rcx]
0x18000a0dd  mov     edx, [rax]
0x18000a0df  mov     [rbp+0B8h], rcx
0x18000a0e6  mov     [rbp+48h], edx
0x18000a0e9  mov     eax, [rbp+48h]
0x18000a0ec  cmp     eax, 0E06D7363h
0x18000a0f1  jnz     short loc_18000A107
0x18000a0f3  mov     rdx, [rbp+0B8h]
0x18000a0fa  mov     ecx, [rbp+48h]
0x18000a0fd  call    _XcptFilter_0
0x18000a102  mov     [rbp+50h], eax
0x18000a105  jmp     short loc_18000A10E
0x18000a107  mov     dword ptr [rbp+50h], 0
0x18000a10e  mov     eax, [rbp+50h]
0x18000a111  add     rsp, 20h
0x18000a115  pop     rbp
0x18000a116  retn
0x18000a118  push    rbp
0x18000a11a  sub     rsp, 20h
0x18000a11e  mov     rbp, rdx
0x18000a121  mov     rax, [rcx]
0x18000a124  mov     edx, [rax]
0x18000a126  mov     [rbp+0C0h], rcx
0x18000a12d  mov     [rbp+58h], edx
0x18000a130  mov     eax, [rbp+58h]
0x18000a133  cmp     eax, 0E06D7363h
0x18000a138  jnz     short loc_18000A14E
0x18000a13a  mov     rdx, [rbp+0C0h]
0x18000a141  mov     ecx, [rbp+58h]
0x18000a144  call    _XcptFilter_0
0x18000a149  mov     [rbp+60h], eax
0x18000a14c  jmp     short loc_18000A155
0x18000a14e  mov     dword ptr [rbp+60h], 0
0x18000a155  mov     eax, [rbp+60h]
0x18000a158  add     rsp, 20h
0x18000a15c  pop     rbp
0x18000a15d  retn
0x18000a15f  push    rbp
0x18000a161  sub     rsp, 20h
0x18000a165  mov     rbp, rdx
0x18000a168  mov     rax, [rcx]
0x18000a16b  mov     edx, [rax]
0x18000a16d  mov     [rbp+0C8h], rcx
0x18000a174  mov     [rbp+68h], edx
0x18000a177  mov     eax, [rbp+68h]
0x18000a17a  cmp     eax, 0E06D7363h
0x18000a17f  jnz     short loc_18000A195
0x18000a181  mov     rdx, [rbp+0C8h]
0x18000a188  mov     ecx, [rbp+68h]
0x18000a18b  call    _XcptFilter_0
0x18000a190  mov     [rbp+70h], eax
0x18000a193  jmp     short loc_18000A19C
0x18000a195  mov     dword ptr [rbp+70h], 0
0x18000a19c  mov     eax, [rbp+70h]
0x18000a19f  add     rsp, 20h
0x18000a1a3  pop     rbp
0x18000a1a4  retn
0x18000a1a6  push    rbp
0x18000a1a8  sub     rsp, 20h
0x18000a1ac  mov     rbp, rdx
0x18000a1af  mov     rax, [rcx]
0x18000a1b2  mov     edx, [rax]
0x18000a1b4  mov     [rbp+0D0h], rcx
0x18000a1bb  mov     [rbp+78h], edx
0x18000a1be  mov     eax, [rbp+78h]
0x18000a1c1  cmp     eax, 0E06D7363h
0x18000a1c6  jnz     short loc_18000A1DF
0x18000a1c8  mov     rdx, [rbp+0D0h]
0x18000a1cf  mov     ecx, [rbp+78h]
0x18000a1d2  call    _XcptFilter_0
0x18000a1d7  mov     [rbp+80h], eax
0x18000a1dd  jmp     short loc_18000A1E9
0x18000a1df  mov     dword ptr [rbp+80h], 0
0x18000a1e9  mov     eax, [rbp+80h]
0x18000a1ef  add     rsp, 20h
0x18000a1f3  pop     rbp
0x18000a1f4  retn
0x18000a1f6  push    rbp
0x18000a1f8  sub     rsp, 20h
0x18000a1fc  mov     rbp, rdx
0x18000a1ff  mov     rax, [rcx]
0x18000a202  mov     edx, [rax]
0x18000a204  mov     [rbp+0D8h], rcx
0x18000a20b  mov     [rbp+88h], edx
0x18000a211  mov     eax, [rbp+88h]
0x18000a217  cmp     eax, 0E06D7363h
0x18000a21c  jnz     short loc_18000A238
0x18000a21e  mov     rdx, [rbp+0D8h]
0x18000a225  mov     ecx, [rbp+88h]
0x18000a22b  call    _XcptFilter_0
0x18000a230  mov     [rbp+90h], eax
0x18000a236  jmp     short loc_18000A242
0x18000a238  mov     dword ptr [rbp+90h], 0
0x18000a242  mov     eax, [rbp+90h]
0x18000a248  add     rsp, 20h
0x18000a24c  pop     rbp
0x18000a24d  retn
0x18000a24f  push    rbp
0x18000a251  sub     rsp, 20h
0x18000a255  mov     rbp, rdx
0x18000a258  mov     rax, [rcx]
0x18000a25b  mov     edx, [rax]
0x18000a25d  mov     [rbp+0E0h], rcx
0x18000a264  mov     [rbp+98h], edx
0x18000a26a  mov     eax, [rbp+98h]
0x18000a270  cmp     eax, 0E06D7363h
0x18000a275  jnz     short loc_18000A291
0x18000a277  mov     rdx, [rbp+0E0h]
0x18000a27e  mov     ecx, [rbp+98h]
0x18000a284  call    _XcptFilter_0
0x18000a289  mov     [rbp+0A0h], eax
0x18000a28f  jmp     short loc_18000A29B
0x18000a291  mov     dword ptr [rbp+0A0h], 0
0x18000a29b  mov     eax, [rbp+0A0h]
0x18000a2a1  add     rsp, 20h
0x18000a2a5  pop     rbp
0x18000a2a6  retn
0x18000a2a8  push    rbp
0x18000a2aa  sub     rsp, 20h
0x18000a2ae  mov     rbp, rdx
0x18000a2b1  cmp     dword ptr [rbp+118h], 1
0x18000a2b8  ja      short loc_18000A2C4
0x18000a2ba  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
