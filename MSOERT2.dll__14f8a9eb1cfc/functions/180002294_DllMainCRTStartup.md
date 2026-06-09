# __DllMainCRTStartup

- ea: `0x180002294`
- end: `0x1800024a0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180002250`

## callees

- `0x180001280`
- `0x180002020`
- `0x180002294`
- `0x1800027e8`
- `0x180013000`

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
  if ( (_DWORD)fdwReason || dword_18001C100 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18001C104 = 1;
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
            if ( dword_18001C104 )
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
0x180002294  mov     [rsp+lpvReserved], r8
0x180002299  mov     [rsp+arg_8], edx
0x18000229d  mov     [rsp+arg_0], rcx
0x1800022a2  push    rbx
0x1800022a3  push    rsi
0x1800022a4  push    rdi
0x1800022a5  sub     rsp, 0F0h
0x1800022ac  mov     edi, edx
0x1800022ae  mov     rsi, rcx
0x1800022b1  mov     ebx, 1
0x1800022b6  cmp     edx, ebx
0x1800022b8  ja      short loc_1800022C0
0x1800022ba  mov     cs:__native_dllmain_reason, edx
0x1800022c0  test    edx, edx
0x1800022c2  jnz     short loc_1800022D7
0x1800022c4  cmp     cs:dword_18001C100, edx
0x1800022ca  jnz     short loc_1800022D7
0x1800022cc  xor     ebx, ebx
0x1800022ce  mov     [rsp+108h+var_E8], ebx
0x1800022d2  jmp     loc_180002484
0x1800022d7  lea     eax, [rdx-1]
0x1800022da  cmp     eax, 1
0x1800022dd  ja      loc_180002364
0x1800022e3  mov     rax, cs:_pRawDllMain
0x1800022ea  test    rax, rax
0x1800022ed  jz      short loc_180002325
0x1800022ef  cmp     edx, 1
0x1800022f2  jnz     short loc_1800022FA
0x1800022f4  mov     cs:dword_18001C104, edx
0x1800022fa  mov     r8, [rsp+108h+lpvReserved]
0x180002302  call    cs:__guard_dispatch_icall_fptr
0x180002308  mov     ebx, eax
0x18000230a  mov     [rsp+108h+var_E8], eax
0x18000230e  jmp     short loc_180002325
0x180002310  xor     ebx, ebx
0x180002312  mov     [rsp+108h+var_E8], ebx
0x180002316  mov     edi, [rsp+108h+arg_8]
0x18000231d  mov     rsi, [rsp+108h+arg_0]
0x180002325  test    ebx, ebx
0x180002327  jz      loc_180002484
0x18000232d  mov     r8, [rsp+108h+lpvReserved]
0x180002335  mov     edx, edi
0x180002337  mov     rcx, rsi
0x18000233a  call    _CRT_INIT
0x18000233f  mov     ebx, eax
0x180002341  mov     [rsp+108h+var_E8], eax
0x180002345  jmp     short loc_18000235C
0x180002347  xor     ebx, ebx
0x180002349  mov     [rsp+108h+var_E8], ebx
0x18000234d  mov     edi, [rsp+108h+arg_8]
0x180002354  mov     rsi, [rsp+108h+arg_0]
0x18000235c  test    ebx, ebx
0x18000235e  jz      loc_180002484
0x180002364  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000236c  mov     edx, edi; fdwReason
0x18000236e  mov     rcx, rsi; hinstDLL
0x180002371  call    DllMain
0x180002376  mov     ebx, eax
0x180002378  mov     [rsp+108h+var_E8], eax
0x18000237c  jmp     short loc_180002393
0x18000237e  xor     ebx, ebx
0x180002380  mov     [rsp+108h+var_E8], ebx
0x180002384  mov     edi, [rsp+108h+arg_8]
0x18000238b  mov     rsi, [rsp+108h+arg_0]
0x180002393  cmp     edi, 1
0x180002396  jnz     short loc_18000240F
0x180002398  test    ebx, ebx
0x18000239a  jnz     short loc_18000240F
0x18000239c  xor     r8d, r8d; lpvReserved
0x18000239f  xor     edx, edx; fdwReason
0x1800023a1  mov     rcx, rsi; hinstDLL
0x1800023a4  call    DllMain
0x1800023a9  jmp     short loc_1800023BE
0x1800023ab  mov     edi, [rsp+108h+arg_8]
0x1800023b2  mov     rsi, [rsp+108h+arg_0]
0x1800023ba  mov     ebx, [rsp+108h+var_E8]
0x1800023be  xor     r8d, r8d
0x1800023c1  xor     edx, edx
0x1800023c3  mov     rcx, rsi
0x1800023c6  call    _CRT_INIT
0x1800023cb  jmp     short loc_1800023E0
0x1800023cd  mov     edi, [rsp+108h+arg_8]
0x1800023d4  mov     rsi, [rsp+108h+arg_0]
0x1800023dc  mov     ebx, [rsp+108h+var_E8]
0x1800023e0  mov     rax, cs:_pRawDllMain
0x1800023e7  test    rax, rax
0x1800023ea  jz      short loc_18000240F
0x1800023ec  xor     r8d, r8d
0x1800023ef  xor     edx, edx
0x1800023f1  mov     rcx, rsi
0x1800023f4  call    cs:__guard_dispatch_icall_fptr
0x1800023fa  jmp     short loc_18000240F
0x1800023fc  mov     edi, [rsp+108h+arg_8]
0x180002403  mov     rsi, [rsp+108h+arg_0]
0x18000240b  mov     ebx, [rsp+108h+var_E8]
0x18000240f  test    edi, edi
0x180002411  jz      short loc_180002418
0x180002413  cmp     edi, 3
0x180002416  jnz     short loc_180002484
0x180002418  mov     r8, [rsp+108h+lpvReserved]
0x180002420  mov     edx, edi
0x180002422  mov     rcx, rsi
0x180002425  call    _CRT_INIT
0x18000242a  mov     ebx, eax
0x18000242c  mov     [rsp+108h+var_E8], eax
0x180002430  jmp     short loc_180002447
0x180002432  xor     ebx, ebx
0x180002434  mov     [rsp+108h+var_E8], ebx
0x180002438  mov     edi, [rsp+108h+arg_8]
0x18000243f  mov     rsi, [rsp+108h+arg_0]
0x180002447  mov     rax, cs:_pRawDllMain
0x18000244e  test    rax, rax
0x180002451  jz      short loc_180002484
0x180002453  cmp     cs:dword_18001C104, 0
0x18000245a  jz      short loc_180002484
0x18000245c  mov     r8, [rsp+108h+lpvReserved]
0x180002464  mov     edx, edi
0x180002466  mov     rcx, rsi
0x180002469  call    cs:__guard_dispatch_icall_fptr
0x18000246f  mov     ebx, eax
0x180002471  mov     [rsp+108h+var_E8], eax
0x180002475  jmp     short loc_180002484
0x180002477  xor     ebx, ebx
0x180002479  mov     [rsp+108h+var_E8], ebx
0x18000247d  mov     edi, [rsp+108h+arg_8]
0x180002484  cmp     edi, 1
0x180002487  ja      short loc_180002493
0x180002489  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180002493  mov     eax, ebx
0x180002495  add     rsp, 0F0h
0x18000249c  pop     rdi
0x18000249d  pop     rsi
0x18000249e  pop     rbx
0x18000249f  retn
0x1800130d0  push    rbp
0x1800130d2  sub     rsp, 20h
0x1800130d6  mov     rbp, rdx
0x1800130d9  mov     rax, [rcx]
0x1800130dc  mov     edx, [rax]
0x1800130de  mov     [rbp+0A8h], rcx
0x1800130e5  mov     [rbp+28h], edx
0x1800130e8  mov     eax, [rbp+28h]
0x1800130eb  cmp     eax, 0E06D7363h
0x1800130f0  jnz     short loc_180013106
0x1800130f2  mov     rdx, [rbp+0A8h]
0x1800130f9  mov     ecx, [rbp+28h]
0x1800130fc  call    _XcptFilter_0
0x180013101  mov     [rbp+30h], eax
0x180013104  jmp     short loc_18001310D
0x180013106  mov     dword ptr [rbp+30h], 0
0x18001310d  mov     eax, [rbp+30h]
0x180013110  add     rsp, 20h
0x180013114  pop     rbp
0x180013115  retn
0x180013117  push    rbp
0x180013119  sub     rsp, 20h
0x18001311d  mov     rbp, rdx
0x180013120  mov     rax, [rcx]
0x180013123  mov     edx, [rax]
0x180013125  mov     [rbp+0B0h], rcx
0x18001312c  mov     [rbp+38h], edx
0x18001312f  mov     eax, [rbp+38h]
0x180013132  cmp     eax, 0E06D7363h
0x180013137  jnz     short loc_18001314D
0x180013139  mov     rdx, [rbp+0B0h]
0x180013140  mov     ecx, [rbp+38h]
0x180013143  call    _XcptFilter_0
0x180013148  mov     [rbp+40h], eax
0x18001314b  jmp     short loc_180013154
0x18001314d  mov     dword ptr [rbp+40h], 0
0x180013154  mov     eax, [rbp+40h]
0x180013157  add     rsp, 20h
0x18001315b  pop     rbp
0x18001315c  retn
0x18001315e  push    rbp
0x180013160  sub     rsp, 20h
0x180013164  mov     rbp, rdx
0x180013167  mov     rax, [rcx]
0x18001316a  mov     edx, [rax]
0x18001316c  mov     [rbp+0B8h], rcx
0x180013173  mov     [rbp+48h], edx
0x180013176  mov     eax, [rbp+48h]
0x180013179  cmp     eax, 0E06D7363h
0x18001317e  jnz     short loc_180013194
0x180013180  mov     rdx, [rbp+0B8h]
0x180013187  mov     ecx, [rbp+48h]
0x18001318a  call    _XcptFilter_0
0x18001318f  mov     [rbp+50h], eax
0x180013192  jmp     short loc_18001319B
0x180013194  mov     dword ptr [rbp+50h], 0
0x18001319b  mov     eax, [rbp+50h]
0x18001319e  add     rsp, 20h
0x1800131a2  pop     rbp
0x1800131a3  retn
0x1800131a5  push    rbp
0x1800131a7  sub     rsp, 20h
0x1800131ab  mov     rbp, rdx
0x1800131ae  mov     rax, [rcx]
0x1800131b1  mov     edx, [rax]
0x1800131b3  mov     [rbp+0C0h], rcx
0x1800131ba  mov     [rbp+58h], edx
0x1800131bd  mov     eax, [rbp+58h]
0x1800131c0  cmp     eax, 0E06D7363h
0x1800131c5  jnz     short loc_1800131DB
0x1800131c7  mov     rdx, [rbp+0C0h]
0x1800131ce  mov     ecx, [rbp+58h]
0x1800131d1  call    _XcptFilter_0
0x1800131d6  mov     [rbp+60h], eax
0x1800131d9  jmp     short loc_1800131E2
0x1800131db  mov     dword ptr [rbp+60h], 0
0x1800131e2  mov     eax, [rbp+60h]
0x1800131e5  add     rsp, 20h
0x1800131e9  pop     rbp
0x1800131ea  retn
0x1800131ec  push    rbp
0x1800131ee  sub     rsp, 20h
0x1800131f2  mov     rbp, rdx
0x1800131f5  mov     rax, [rcx]
0x1800131f8  mov     edx, [rax]
0x1800131fa  mov     [rbp+0C8h], rcx
0x180013201  mov     [rbp+68h], edx
0x180013204  mov     eax, [rbp+68h]
0x180013207  cmp     eax, 0E06D7363h
0x18001320c  jnz     short loc_180013222
0x18001320e  mov     rdx, [rbp+0C8h]
0x180013215  mov     ecx, [rbp+68h]
0x180013218  call    _XcptFilter_0
0x18001321d  mov     [rbp+70h], eax
0x180013220  jmp     short loc_180013229
0x180013222  mov     dword ptr [rbp+70h], 0
0x180013229  mov     eax, [rbp+70h]
0x18001322c  add     rsp, 20h
0x180013230  pop     rbp
0x180013231  retn
0x180013233  push    rbp
0x180013235  sub     rsp, 20h
0x180013239  mov     rbp, rdx
0x18001323c  mov     rax, [rcx]
0x18001323f  mov     edx, [rax]
0x180013241  mov     [rbp+0D0h], rcx
0x180013248  mov     [rbp+78h], edx
0x18001324b  mov     eax, [rbp+78h]
0x18001324e  cmp     eax, 0E06D7363h
0x180013253  jnz     short loc_18001326C
0x180013255  mov     rdx, [rbp+0D0h]
0x18001325c  mov     ecx, [rbp+78h]
0x18001325f  call    _XcptFilter_0
0x180013264  mov     [rbp+80h], eax
0x18001326a  jmp     short loc_180013276
0x18001326c  mov     dword ptr [rbp+80h], 0
0x180013276  mov     eax, [rbp+80h]
0x18001327c  add     rsp, 20h
0x180013280  pop     rbp
0x180013281  retn
0x180013283  push    rbp
0x180013285  sub     rsp, 20h
0x180013289  mov     rbp, rdx
0x18001328c  mov     rax, [rcx]
0x18001328f  mov     edx, [rax]
0x180013291  mov     [rbp+0D8h], rcx
0x180013298  mov     [rbp+88h], edx
0x18001329e  mov     eax, [rbp+88h]
0x1800132a4  cmp     eax, 0E06D7363h
0x1800132a9  jnz     short loc_1800132C5
0x1800132ab  mov     rdx, [rbp+0D8h]
0x1800132b2  mov     ecx, [rbp+88h]
0x1800132b8  call    _XcptFilter_0
0x1800132bd  mov     [rbp+90h], eax
0x1800132c3  jmp     short loc_1800132CF
0x1800132c5  mov     dword ptr [rbp+90h], 0
0x1800132cf  mov     eax, [rbp+90h]
0x1800132d5  add     rsp, 20h
0x1800132d9  pop     rbp
0x1800132da  retn
0x1800132dc  push    rbp
0x1800132de  sub     rsp, 20h
0x1800132e2  mov     rbp, rdx
0x1800132e5  mov     rax, [rcx]
0x1800132e8  mov     edx, [rax]
0x1800132ea  mov     [rbp+0E0h], rcx
0x1800132f1  mov     [rbp+98h], edx
0x1800132f7  mov     eax, [rbp+98h]
0x1800132fd  cmp     eax, 0E06D7363h
0x180013302  jnz     short loc_18001331E
0x180013304  mov     rdx, [rbp+0E0h]
0x18001330b  mov     ecx, [rbp+98h]
0x180013311  call    _XcptFilter_0
0x180013316  mov     [rbp+0A0h], eax
0x18001331c  jmp     short loc_180013328
0x18001331e  mov     dword ptr [rbp+0A0h], 0
0x180013328  mov     eax, [rbp+0A0h]
0x18001332e  add     rsp, 20h
0x180013332  pop     rbp
0x180013333  retn
0x180013335  push    rbp
0x180013337  sub     rsp, 20h
0x18001333b  mov     rbp, rdx
0x18001333e  cmp     dword ptr [rbp+118h], 1
0x180013345  ja      short loc_180013351
0x180013347  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
