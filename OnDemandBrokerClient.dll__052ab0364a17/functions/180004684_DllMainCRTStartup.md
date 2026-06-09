# __DllMainCRTStartup

- ea: `0x180004684`
- end: `0x180004890`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180004640`

## callees

- `0x1800042e0`
- `0x180004410`
- `0x180004684`
- `0x1800048ca`
- `0x1800065b0`

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
  if ( (_DWORD)fdwReason || dword_18000C0C0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18000C0C4 = 1;
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
            if ( dword_18000C0C4 )
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
0x180004684  mov     [rsp+lpvReserved], r8
0x180004689  mov     [rsp+arg_8], edx
0x18000468d  mov     [rsp+arg_0], rcx
0x180004692  push    rbx
0x180004693  push    rsi
0x180004694  push    rdi
0x180004695  sub     rsp, 0F0h
0x18000469c  mov     edi, edx
0x18000469e  mov     rsi, rcx
0x1800046a1  mov     ebx, 1
0x1800046a6  cmp     edx, ebx
0x1800046a8  ja      short loc_1800046B0
0x1800046aa  mov     cs:__native_dllmain_reason, edx
0x1800046b0  test    edx, edx
0x1800046b2  jnz     short loc_1800046C7
0x1800046b4  cmp     cs:dword_18000C0C0, edx
0x1800046ba  jnz     short loc_1800046C7
0x1800046bc  xor     ebx, ebx
0x1800046be  mov     [rsp+108h+var_E8], ebx
0x1800046c2  jmp     loc_180004874
0x1800046c7  lea     eax, [rdx-1]
0x1800046ca  cmp     eax, 1
0x1800046cd  ja      loc_180004754
0x1800046d3  mov     rax, cs:_pRawDllMain
0x1800046da  test    rax, rax
0x1800046dd  jz      short loc_180004715
0x1800046df  cmp     edx, 1
0x1800046e2  jnz     short loc_1800046EA
0x1800046e4  mov     cs:dword_18000C0C4, edx
0x1800046ea  mov     r8, [rsp+108h+lpvReserved]
0x1800046f2  call    cs:__guard_dispatch_icall_fptr
0x1800046f8  mov     ebx, eax
0x1800046fa  mov     [rsp+108h+var_E8], eax
0x1800046fe  jmp     short loc_180004715
0x180004700  xor     ebx, ebx
0x180004702  mov     [rsp+108h+var_E8], ebx
0x180004706  mov     edi, [rsp+108h+arg_8]
0x18000470d  mov     rsi, [rsp+108h+arg_0]
0x180004715  test    ebx, ebx
0x180004717  jz      loc_180004874
0x18000471d  mov     r8, [rsp+108h+lpvReserved]
0x180004725  mov     edx, edi
0x180004727  mov     rcx, rsi
0x18000472a  call    _CRT_INIT
0x18000472f  mov     ebx, eax
0x180004731  mov     [rsp+108h+var_E8], eax
0x180004735  jmp     short loc_18000474C
0x180004737  xor     ebx, ebx
0x180004739  mov     [rsp+108h+var_E8], ebx
0x18000473d  mov     edi, [rsp+108h+arg_8]
0x180004744  mov     rsi, [rsp+108h+arg_0]
0x18000474c  test    ebx, ebx
0x18000474e  jz      loc_180004874
0x180004754  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000475c  mov     edx, edi; fdwReason
0x18000475e  mov     rcx, rsi; hinstDLL
0x180004761  call    DllMain
0x180004766  mov     ebx, eax
0x180004768  mov     [rsp+108h+var_E8], eax
0x18000476c  jmp     short loc_180004783
0x18000476e  xor     ebx, ebx
0x180004770  mov     [rsp+108h+var_E8], ebx
0x180004774  mov     edi, [rsp+108h+arg_8]
0x18000477b  mov     rsi, [rsp+108h+arg_0]
0x180004783  cmp     edi, 1
0x180004786  jnz     short loc_1800047FF
0x180004788  test    ebx, ebx
0x18000478a  jnz     short loc_1800047FF
0x18000478c  xor     r8d, r8d; lpvReserved
0x18000478f  xor     edx, edx; fdwReason
0x180004791  mov     rcx, rsi; hinstDLL
0x180004794  call    DllMain
0x180004799  jmp     short loc_1800047AE
0x18000479b  mov     edi, [rsp+108h+arg_8]
0x1800047a2  mov     rsi, [rsp+108h+arg_0]
0x1800047aa  mov     ebx, [rsp+108h+var_E8]
0x1800047ae  xor     r8d, r8d
0x1800047b1  xor     edx, edx
0x1800047b3  mov     rcx, rsi
0x1800047b6  call    _CRT_INIT
0x1800047bb  jmp     short loc_1800047D0
0x1800047bd  mov     edi, [rsp+108h+arg_8]
0x1800047c4  mov     rsi, [rsp+108h+arg_0]
0x1800047cc  mov     ebx, [rsp+108h+var_E8]
0x1800047d0  mov     rax, cs:_pRawDllMain
0x1800047d7  test    rax, rax
0x1800047da  jz      short loc_1800047FF
0x1800047dc  xor     r8d, r8d
0x1800047df  xor     edx, edx
0x1800047e1  mov     rcx, rsi
0x1800047e4  call    cs:__guard_dispatch_icall_fptr
0x1800047ea  jmp     short loc_1800047FF
0x1800047ec  mov     edi, [rsp+108h+arg_8]
0x1800047f3  mov     rsi, [rsp+108h+arg_0]
0x1800047fb  mov     ebx, [rsp+108h+var_E8]
0x1800047ff  test    edi, edi
0x180004801  jz      short loc_180004808
0x180004803  cmp     edi, 3
0x180004806  jnz     short loc_180004874
0x180004808  mov     r8, [rsp+108h+lpvReserved]
0x180004810  mov     edx, edi
0x180004812  mov     rcx, rsi
0x180004815  call    _CRT_INIT
0x18000481a  mov     ebx, eax
0x18000481c  mov     [rsp+108h+var_E8], eax
0x180004820  jmp     short loc_180004837
0x180004822  xor     ebx, ebx
0x180004824  mov     [rsp+108h+var_E8], ebx
0x180004828  mov     edi, [rsp+108h+arg_8]
0x18000482f  mov     rsi, [rsp+108h+arg_0]
0x180004837  mov     rax, cs:_pRawDllMain
0x18000483e  test    rax, rax
0x180004841  jz      short loc_180004874
0x180004843  cmp     cs:dword_18000C0C4, 0
0x18000484a  jz      short loc_180004874
0x18000484c  mov     r8, [rsp+108h+lpvReserved]
0x180004854  mov     edx, edi
0x180004856  mov     rcx, rsi
0x180004859  call    cs:__guard_dispatch_icall_fptr
0x18000485f  mov     ebx, eax
0x180004861  mov     [rsp+108h+var_E8], eax
0x180004865  jmp     short loc_180004874
0x180004867  xor     ebx, ebx
0x180004869  mov     [rsp+108h+var_E8], ebx
0x18000486d  mov     edi, [rsp+108h+arg_8]
0x180004874  cmp     edi, 1
0x180004877  ja      short loc_180004883
0x180004879  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180004883  mov     eax, ebx
0x180004885  add     rsp, 0F0h
0x18000488c  pop     rdi
0x18000488d  pop     rsi
0x18000488e  pop     rbx
0x18000488f  retn
0x180006792  push    rbp
0x180006794  sub     rsp, 20h
0x180006798  mov     rbp, rdx
0x18000679b  mov     rax, [rcx]
0x18000679e  mov     edx, [rax]
0x1800067a0  mov     [rbp+0A8h], rcx
0x1800067a7  mov     [rbp+28h], edx
0x1800067aa  mov     eax, [rbp+28h]
0x1800067ad  cmp     eax, 0E06D7363h
0x1800067b2  jnz     short loc_1800067C8
0x1800067b4  mov     rdx, [rbp+0A8h]
0x1800067bb  mov     ecx, [rbp+28h]
0x1800067be  call    _XcptFilter_0
0x1800067c3  mov     [rbp+30h], eax
0x1800067c6  jmp     short loc_1800067CF
0x1800067c8  mov     dword ptr [rbp+30h], 0
0x1800067cf  mov     eax, [rbp+30h]
0x1800067d2  add     rsp, 20h
0x1800067d6  pop     rbp
0x1800067d7  retn
0x1800067d9  push    rbp
0x1800067db  sub     rsp, 20h
0x1800067df  mov     rbp, rdx
0x1800067e2  mov     rax, [rcx]
0x1800067e5  mov     edx, [rax]
0x1800067e7  mov     [rbp+0B0h], rcx
0x1800067ee  mov     [rbp+38h], edx
0x1800067f1  mov     eax, [rbp+38h]
0x1800067f4  cmp     eax, 0E06D7363h
0x1800067f9  jnz     short loc_18000680F
0x1800067fb  mov     rdx, [rbp+0B0h]
0x180006802  mov     ecx, [rbp+38h]
0x180006805  call    _XcptFilter_0
0x18000680a  mov     [rbp+40h], eax
0x18000680d  jmp     short loc_180006816
0x18000680f  mov     dword ptr [rbp+40h], 0
0x180006816  mov     eax, [rbp+40h]
0x180006819  add     rsp, 20h
0x18000681d  pop     rbp
0x18000681e  retn
0x180006820  push    rbp
0x180006822  sub     rsp, 20h
0x180006826  mov     rbp, rdx
0x180006829  mov     rax, [rcx]
0x18000682c  mov     edx, [rax]
0x18000682e  mov     [rbp+0B8h], rcx
0x180006835  mov     [rbp+48h], edx
0x180006838  mov     eax, [rbp+48h]
0x18000683b  cmp     eax, 0E06D7363h
0x180006840  jnz     short loc_180006856
0x180006842  mov     rdx, [rbp+0B8h]
0x180006849  mov     ecx, [rbp+48h]
0x18000684c  call    _XcptFilter_0
0x180006851  mov     [rbp+50h], eax
0x180006854  jmp     short loc_18000685D
0x180006856  mov     dword ptr [rbp+50h], 0
0x18000685d  mov     eax, [rbp+50h]
0x180006860  add     rsp, 20h
0x180006864  pop     rbp
0x180006865  retn
0x180006867  push    rbp
0x180006869  sub     rsp, 20h
0x18000686d  mov     rbp, rdx
0x180006870  mov     rax, [rcx]
0x180006873  mov     edx, [rax]
0x180006875  mov     [rbp+0C0h], rcx
0x18000687c  mov     [rbp+58h], edx
0x18000687f  mov     eax, [rbp+58h]
0x180006882  cmp     eax, 0E06D7363h
0x180006887  jnz     short loc_18000689D
0x180006889  mov     rdx, [rbp+0C0h]
0x180006890  mov     ecx, [rbp+58h]
0x180006893  call    _XcptFilter_0
0x180006898  mov     [rbp+60h], eax
0x18000689b  jmp     short loc_1800068A4
0x18000689d  mov     dword ptr [rbp+60h], 0
0x1800068a4  mov     eax, [rbp+60h]
0x1800068a7  add     rsp, 20h
0x1800068ab  pop     rbp
0x1800068ac  retn
0x1800068ae  push    rbp
0x1800068b0  sub     rsp, 20h
0x1800068b4  mov     rbp, rdx
0x1800068b7  mov     rax, [rcx]
0x1800068ba  mov     edx, [rax]
0x1800068bc  mov     [rbp+0C8h], rcx
0x1800068c3  mov     [rbp+68h], edx
0x1800068c6  mov     eax, [rbp+68h]
0x1800068c9  cmp     eax, 0E06D7363h
0x1800068ce  jnz     short loc_1800068E4
0x1800068d0  mov     rdx, [rbp+0C8h]
0x1800068d7  mov     ecx, [rbp+68h]
0x1800068da  call    _XcptFilter_0
0x1800068df  mov     [rbp+70h], eax
0x1800068e2  jmp     short loc_1800068EB
0x1800068e4  mov     dword ptr [rbp+70h], 0
0x1800068eb  mov     eax, [rbp+70h]
0x1800068ee  add     rsp, 20h
0x1800068f2  pop     rbp
0x1800068f3  retn
0x1800068f5  push    rbp
0x1800068f7  sub     rsp, 20h
0x1800068fb  mov     rbp, rdx
0x1800068fe  mov     rax, [rcx]
0x180006901  mov     edx, [rax]
0x180006903  mov     [rbp+0D0h], rcx
0x18000690a  mov     [rbp+78h], edx
0x18000690d  mov     eax, [rbp+78h]
0x180006910  cmp     eax, 0E06D7363h
0x180006915  jnz     short loc_18000692E
0x180006917  mov     rdx, [rbp+0D0h]
0x18000691e  mov     ecx, [rbp+78h]
0x180006921  call    _XcptFilter_0
0x180006926  mov     [rbp+80h], eax
0x18000692c  jmp     short loc_180006938
0x18000692e  mov     dword ptr [rbp+80h], 0
0x180006938  mov     eax, [rbp+80h]
0x18000693e  add     rsp, 20h
0x180006942  pop     rbp
0x180006943  retn
0x180006945  push    rbp
0x180006947  sub     rsp, 20h
0x18000694b  mov     rbp, rdx
0x18000694e  mov     rax, [rcx]
0x180006951  mov     edx, [rax]
0x180006953  mov     [rbp+0D8h], rcx
0x18000695a  mov     [rbp+88h], edx
0x180006960  mov     eax, [rbp+88h]
0x180006966  cmp     eax, 0E06D7363h
0x18000696b  jnz     short loc_180006987
0x18000696d  mov     rdx, [rbp+0D8h]
0x180006974  mov     ecx, [rbp+88h]
0x18000697a  call    _XcptFilter_0
0x18000697f  mov     [rbp+90h], eax
0x180006985  jmp     short loc_180006991
0x180006987  mov     dword ptr [rbp+90h], 0
0x180006991  mov     eax, [rbp+90h]
0x180006997  add     rsp, 20h
0x18000699b  pop     rbp
0x18000699c  retn
0x18000699e  push    rbp
0x1800069a0  sub     rsp, 20h
0x1800069a4  mov     rbp, rdx
0x1800069a7  mov     rax, [rcx]
0x1800069aa  mov     edx, [rax]
0x1800069ac  mov     [rbp+0E0h], rcx
0x1800069b3  mov     [rbp+98h], edx
0x1800069b9  mov     eax, [rbp+98h]
0x1800069bf  cmp     eax, 0E06D7363h
0x1800069c4  jnz     short loc_1800069E0
0x1800069c6  mov     rdx, [rbp+0E0h]
0x1800069cd  mov     ecx, [rbp+98h]
0x1800069d3  call    _XcptFilter_0
0x1800069d8  mov     [rbp+0A0h], eax
0x1800069de  jmp     short loc_1800069EA
0x1800069e0  mov     dword ptr [rbp+0A0h], 0
0x1800069ea  mov     eax, [rbp+0A0h]
0x1800069f0  add     rsp, 20h
0x1800069f4  pop     rbp
0x1800069f5  retn
0x1800069f7  push    rbp
0x1800069f9  sub     rsp, 20h
0x1800069fd  mov     rbp, rdx
0x180006a00  cmp     dword ptr [rbp+118h], 1
0x180006a07  ja      short loc_180006A13
0x180006a09  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
