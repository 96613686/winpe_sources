# __DllMainCRTStartup

- ea: `0x1800013a4`
- end: `0x1800015b0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001360`

## callees

- `0x180001130`
- `0x1800013a4`
- `0x180001928`
- `0x180009b20`
- `0x180013600`

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
  if ( (_DWORD)fdwReason || dword_18001C140 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18001C144 = 1;
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
            if ( dword_18001C144 )
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
0x1800013a4  mov     [rsp+lpvReserved], r8
0x1800013a9  mov     [rsp+arg_8], edx
0x1800013ad  mov     [rsp+arg_0], rcx
0x1800013b2  push    rbx
0x1800013b3  push    rsi
0x1800013b4  push    rdi
0x1800013b5  sub     rsp, 0F0h
0x1800013bc  mov     edi, edx
0x1800013be  mov     rsi, rcx
0x1800013c1  mov     ebx, 1
0x1800013c6  cmp     edx, ebx
0x1800013c8  ja      short loc_1800013D0
0x1800013ca  mov     cs:__native_dllmain_reason, edx
0x1800013d0  test    edx, edx
0x1800013d2  jnz     short loc_1800013E7
0x1800013d4  cmp     cs:dword_18001C140, edx
0x1800013da  jnz     short loc_1800013E7
0x1800013dc  xor     ebx, ebx
0x1800013de  mov     [rsp+108h+var_E8], ebx
0x1800013e2  jmp     loc_180001594
0x1800013e7  lea     eax, [rdx-1]
0x1800013ea  cmp     eax, 1
0x1800013ed  ja      loc_180001474
0x1800013f3  mov     rax, cs:_pRawDllMain
0x1800013fa  test    rax, rax
0x1800013fd  jz      short loc_180001435
0x1800013ff  cmp     edx, 1
0x180001402  jnz     short loc_18000140A
0x180001404  mov     cs:dword_18001C144, edx
0x18000140a  mov     r8, [rsp+108h+lpvReserved]
0x180001412  call    cs:__guard_dispatch_icall_fptr
0x180001418  mov     ebx, eax
0x18000141a  mov     [rsp+108h+var_E8], eax
0x18000141e  jmp     short loc_180001435
0x180001420  xor     ebx, ebx
0x180001422  mov     [rsp+108h+var_E8], ebx
0x180001426  mov     edi, [rsp+108h+arg_8]
0x18000142d  mov     rsi, [rsp+108h+arg_0]
0x180001435  test    ebx, ebx
0x180001437  jz      loc_180001594
0x18000143d  mov     r8, [rsp+108h+lpvReserved]
0x180001445  mov     edx, edi
0x180001447  mov     rcx, rsi
0x18000144a  call    _CRT_INIT
0x18000144f  mov     ebx, eax
0x180001451  mov     [rsp+108h+var_E8], eax
0x180001455  jmp     short loc_18000146C
0x180001457  xor     ebx, ebx
0x180001459  mov     [rsp+108h+var_E8], ebx
0x18000145d  mov     edi, [rsp+108h+arg_8]
0x180001464  mov     rsi, [rsp+108h+arg_0]
0x18000146c  test    ebx, ebx
0x18000146e  jz      loc_180001594
0x180001474  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000147c  mov     edx, edi; fdwReason
0x18000147e  mov     rcx, rsi; hinstDLL
0x180001481  call    DllMain
0x180001486  mov     ebx, eax
0x180001488  mov     [rsp+108h+var_E8], eax
0x18000148c  jmp     short loc_1800014A3
0x18000148e  xor     ebx, ebx
0x180001490  mov     [rsp+108h+var_E8], ebx
0x180001494  mov     edi, [rsp+108h+arg_8]
0x18000149b  mov     rsi, [rsp+108h+arg_0]
0x1800014a3  cmp     edi, 1
0x1800014a6  jnz     short loc_18000151F
0x1800014a8  test    ebx, ebx
0x1800014aa  jnz     short loc_18000151F
0x1800014ac  xor     r8d, r8d; lpvReserved
0x1800014af  xor     edx, edx; fdwReason
0x1800014b1  mov     rcx, rsi; hinstDLL
0x1800014b4  call    DllMain
0x1800014b9  jmp     short loc_1800014CE
0x1800014bb  mov     edi, [rsp+108h+arg_8]
0x1800014c2  mov     rsi, [rsp+108h+arg_0]
0x1800014ca  mov     ebx, [rsp+108h+var_E8]
0x1800014ce  xor     r8d, r8d
0x1800014d1  xor     edx, edx
0x1800014d3  mov     rcx, rsi
0x1800014d6  call    _CRT_INIT
0x1800014db  jmp     short loc_1800014F0
0x1800014dd  mov     edi, [rsp+108h+arg_8]
0x1800014e4  mov     rsi, [rsp+108h+arg_0]
0x1800014ec  mov     ebx, [rsp+108h+var_E8]
0x1800014f0  mov     rax, cs:_pRawDllMain
0x1800014f7  test    rax, rax
0x1800014fa  jz      short loc_18000151F
0x1800014fc  xor     r8d, r8d
0x1800014ff  xor     edx, edx
0x180001501  mov     rcx, rsi
0x180001504  call    cs:__guard_dispatch_icall_fptr
0x18000150a  jmp     short loc_18000151F
0x18000150c  mov     edi, [rsp+108h+arg_8]
0x180001513  mov     rsi, [rsp+108h+arg_0]
0x18000151b  mov     ebx, [rsp+108h+var_E8]
0x18000151f  test    edi, edi
0x180001521  jz      short loc_180001528
0x180001523  cmp     edi, 3
0x180001526  jnz     short loc_180001594
0x180001528  mov     r8, [rsp+108h+lpvReserved]
0x180001530  mov     edx, edi
0x180001532  mov     rcx, rsi
0x180001535  call    _CRT_INIT
0x18000153a  mov     ebx, eax
0x18000153c  mov     [rsp+108h+var_E8], eax
0x180001540  jmp     short loc_180001557
0x180001542  xor     ebx, ebx
0x180001544  mov     [rsp+108h+var_E8], ebx
0x180001548  mov     edi, [rsp+108h+arg_8]
0x18000154f  mov     rsi, [rsp+108h+arg_0]
0x180001557  mov     rax, cs:_pRawDllMain
0x18000155e  test    rax, rax
0x180001561  jz      short loc_180001594
0x180001563  cmp     cs:dword_18001C144, 0
0x18000156a  jz      short loc_180001594
0x18000156c  mov     r8, [rsp+108h+lpvReserved]
0x180001574  mov     edx, edi
0x180001576  mov     rcx, rsi
0x180001579  call    cs:__guard_dispatch_icall_fptr
0x18000157f  mov     ebx, eax
0x180001581  mov     [rsp+108h+var_E8], eax
0x180001585  jmp     short loc_180001594
0x180001587  xor     ebx, ebx
0x180001589  mov     [rsp+108h+var_E8], ebx
0x18000158d  mov     edi, [rsp+108h+arg_8]
0x180001594  cmp     edi, 1
0x180001597  ja      short loc_1800015A3
0x180001599  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800015a3  mov     eax, ebx
0x1800015a5  add     rsp, 0F0h
0x1800015ac  pop     rdi
0x1800015ad  pop     rsi
0x1800015ae  pop     rbx
0x1800015af  retn
0x1800136d0  push    rbp
0x1800136d2  sub     rsp, 20h
0x1800136d6  mov     rbp, rdx
0x1800136d9  mov     rax, [rcx]
0x1800136dc  mov     edx, [rax]
0x1800136de  mov     [rbp+0A8h], rcx
0x1800136e5  mov     [rbp+28h], edx
0x1800136e8  mov     eax, [rbp+28h]
0x1800136eb  cmp     eax, 0E06D7363h
0x1800136f0  jnz     short loc_180013706
0x1800136f2  mov     rdx, [rbp+0A8h]
0x1800136f9  mov     ecx, [rbp+28h]
0x1800136fc  call    _XcptFilter_0
0x180013701  mov     [rbp+30h], eax
0x180013704  jmp     short loc_18001370D
0x180013706  mov     dword ptr [rbp+30h], 0
0x18001370d  mov     eax, [rbp+30h]
0x180013710  add     rsp, 20h
0x180013714  pop     rbp
0x180013715  retn
0x180013717  push    rbp
0x180013719  sub     rsp, 20h
0x18001371d  mov     rbp, rdx
0x180013720  mov     rax, [rcx]
0x180013723  mov     edx, [rax]
0x180013725  mov     [rbp+0B0h], rcx
0x18001372c  mov     [rbp+38h], edx
0x18001372f  mov     eax, [rbp+38h]
0x180013732  cmp     eax, 0E06D7363h
0x180013737  jnz     short loc_18001374D
0x180013739  mov     rdx, [rbp+0B0h]
0x180013740  mov     ecx, [rbp+38h]
0x180013743  call    _XcptFilter_0
0x180013748  mov     [rbp+40h], eax
0x18001374b  jmp     short loc_180013754
0x18001374d  mov     dword ptr [rbp+40h], 0
0x180013754  mov     eax, [rbp+40h]
0x180013757  add     rsp, 20h
0x18001375b  pop     rbp
0x18001375c  retn
0x18001375e  push    rbp
0x180013760  sub     rsp, 20h
0x180013764  mov     rbp, rdx
0x180013767  mov     rax, [rcx]
0x18001376a  mov     edx, [rax]
0x18001376c  mov     [rbp+0B8h], rcx
0x180013773  mov     [rbp+48h], edx
0x180013776  mov     eax, [rbp+48h]
0x180013779  cmp     eax, 0E06D7363h
0x18001377e  jnz     short loc_180013794
0x180013780  mov     rdx, [rbp+0B8h]
0x180013787  mov     ecx, [rbp+48h]
0x18001378a  call    _XcptFilter_0
0x18001378f  mov     [rbp+50h], eax
0x180013792  jmp     short loc_18001379B
0x180013794  mov     dword ptr [rbp+50h], 0
0x18001379b  mov     eax, [rbp+50h]
0x18001379e  add     rsp, 20h
0x1800137a2  pop     rbp
0x1800137a3  retn
0x1800137a5  push    rbp
0x1800137a7  sub     rsp, 20h
0x1800137ab  mov     rbp, rdx
0x1800137ae  mov     rax, [rcx]
0x1800137b1  mov     edx, [rax]
0x1800137b3  mov     [rbp+0C0h], rcx
0x1800137ba  mov     [rbp+58h], edx
0x1800137bd  mov     eax, [rbp+58h]
0x1800137c0  cmp     eax, 0E06D7363h
0x1800137c5  jnz     short loc_1800137DB
0x1800137c7  mov     rdx, [rbp+0C0h]
0x1800137ce  mov     ecx, [rbp+58h]
0x1800137d1  call    _XcptFilter_0
0x1800137d6  mov     [rbp+60h], eax
0x1800137d9  jmp     short loc_1800137E2
0x1800137db  mov     dword ptr [rbp+60h], 0
0x1800137e2  mov     eax, [rbp+60h]
0x1800137e5  add     rsp, 20h
0x1800137e9  pop     rbp
0x1800137ea  retn
0x1800137ec  push    rbp
0x1800137ee  sub     rsp, 20h
0x1800137f2  mov     rbp, rdx
0x1800137f5  mov     rax, [rcx]
0x1800137f8  mov     edx, [rax]
0x1800137fa  mov     [rbp+0C8h], rcx
0x180013801  mov     [rbp+68h], edx
0x180013804  mov     eax, [rbp+68h]
0x180013807  cmp     eax, 0E06D7363h
0x18001380c  jnz     short loc_180013822
0x18001380e  mov     rdx, [rbp+0C8h]
0x180013815  mov     ecx, [rbp+68h]
0x180013818  call    _XcptFilter_0
0x18001381d  mov     [rbp+70h], eax
0x180013820  jmp     short loc_180013829
0x180013822  mov     dword ptr [rbp+70h], 0
0x180013829  mov     eax, [rbp+70h]
0x18001382c  add     rsp, 20h
0x180013830  pop     rbp
0x180013831  retn
0x180013833  push    rbp
0x180013835  sub     rsp, 20h
0x180013839  mov     rbp, rdx
0x18001383c  mov     rax, [rcx]
0x18001383f  mov     edx, [rax]
0x180013841  mov     [rbp+0D0h], rcx
0x180013848  mov     [rbp+78h], edx
0x18001384b  mov     eax, [rbp+78h]
0x18001384e  cmp     eax, 0E06D7363h
0x180013853  jnz     short loc_18001386C
0x180013855  mov     rdx, [rbp+0D0h]
0x18001385c  mov     ecx, [rbp+78h]
0x18001385f  call    _XcptFilter_0
0x180013864  mov     [rbp+80h], eax
0x18001386a  jmp     short loc_180013876
0x18001386c  mov     dword ptr [rbp+80h], 0
0x180013876  mov     eax, [rbp+80h]
0x18001387c  add     rsp, 20h
0x180013880  pop     rbp
0x180013881  retn
0x180013883  push    rbp
0x180013885  sub     rsp, 20h
0x180013889  mov     rbp, rdx
0x18001388c  mov     rax, [rcx]
0x18001388f  mov     edx, [rax]
0x180013891  mov     [rbp+0D8h], rcx
0x180013898  mov     [rbp+88h], edx
0x18001389e  mov     eax, [rbp+88h]
0x1800138a4  cmp     eax, 0E06D7363h
0x1800138a9  jnz     short loc_1800138C5
0x1800138ab  mov     rdx, [rbp+0D8h]
0x1800138b2  mov     ecx, [rbp+88h]
0x1800138b8  call    _XcptFilter_0
0x1800138bd  mov     [rbp+90h], eax
0x1800138c3  jmp     short loc_1800138CF
0x1800138c5  mov     dword ptr [rbp+90h], 0
0x1800138cf  mov     eax, [rbp+90h]
0x1800138d5  add     rsp, 20h
0x1800138d9  pop     rbp
0x1800138da  retn
0x1800138dc  push    rbp
0x1800138de  sub     rsp, 20h
0x1800138e2  mov     rbp, rdx
0x1800138e5  mov     rax, [rcx]
0x1800138e8  mov     edx, [rax]
0x1800138ea  mov     [rbp+0E0h], rcx
0x1800138f1  mov     [rbp+98h], edx
0x1800138f7  mov     eax, [rbp+98h]
0x1800138fd  cmp     eax, 0E06D7363h
0x180013902  jnz     short loc_18001391E
0x180013904  mov     rdx, [rbp+0E0h]
0x18001390b  mov     ecx, [rbp+98h]
0x180013911  call    _XcptFilter_0
0x180013916  mov     [rbp+0A0h], eax
0x18001391c  jmp     short loc_180013928
0x18001391e  mov     dword ptr [rbp+0A0h], 0
0x180013928  mov     eax, [rbp+0A0h]
0x18001392e  add     rsp, 20h
0x180013932  pop     rbp
0x180013933  retn
0x180013935  push    rbp
0x180013937  sub     rsp, 20h
0x18001393b  mov     rbp, rdx
0x18001393e  cmp     dword ptr [rbp+118h], 1
0x180013945  ja      short loc_180013951
0x180013947  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
