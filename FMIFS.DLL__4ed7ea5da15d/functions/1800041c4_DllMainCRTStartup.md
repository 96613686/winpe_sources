# __DllMainCRTStartup

- ea: `0x1800041c4`
- end: `0x1800043d0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180004180`

## callees

- `0x180003f50`
- `0x1800041c4`
- `0x1800043e2`
- `0x180007058`
- `0x1800097c0`

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
  if ( (_DWORD)fdwReason || dword_18000F1C0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18000F1C4 = 1;
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
            if ( dword_18000F1C4 )
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
0x1800041c4  mov     [rsp+lpvReserved], r8
0x1800041c9  mov     [rsp+arg_8], edx
0x1800041cd  mov     [rsp+arg_0], rcx
0x1800041d2  push    rbx
0x1800041d3  push    rsi
0x1800041d4  push    rdi
0x1800041d5  sub     rsp, 0F0h
0x1800041dc  mov     edi, edx
0x1800041de  mov     rsi, rcx
0x1800041e1  mov     ebx, 1
0x1800041e6  cmp     edx, ebx
0x1800041e8  ja      short loc_1800041F0
0x1800041ea  mov     cs:__native_dllmain_reason, edx
0x1800041f0  test    edx, edx
0x1800041f2  jnz     short loc_180004207
0x1800041f4  cmp     cs:dword_18000F1C0, edx
0x1800041fa  jnz     short loc_180004207
0x1800041fc  xor     ebx, ebx
0x1800041fe  mov     [rsp+108h+var_E8], ebx
0x180004202  jmp     loc_1800043B4
0x180004207  lea     eax, [rdx-1]
0x18000420a  cmp     eax, 1
0x18000420d  ja      loc_180004294
0x180004213  mov     rax, cs:_pRawDllMain
0x18000421a  test    rax, rax
0x18000421d  jz      short loc_180004255
0x18000421f  cmp     edx, 1
0x180004222  jnz     short loc_18000422A
0x180004224  mov     cs:dword_18000F1C4, edx
0x18000422a  mov     r8, [rsp+108h+lpvReserved]
0x180004232  call    cs:__guard_dispatch_icall_fptr
0x180004238  mov     ebx, eax
0x18000423a  mov     [rsp+108h+var_E8], eax
0x18000423e  jmp     short loc_180004255
0x180004240  xor     ebx, ebx
0x180004242  mov     [rsp+108h+var_E8], ebx
0x180004246  mov     edi, [rsp+108h+arg_8]
0x18000424d  mov     rsi, [rsp+108h+arg_0]
0x180004255  test    ebx, ebx
0x180004257  jz      loc_1800043B4
0x18000425d  mov     r8, [rsp+108h+lpvReserved]
0x180004265  mov     edx, edi
0x180004267  mov     rcx, rsi
0x18000426a  call    _CRT_INIT
0x18000426f  mov     ebx, eax
0x180004271  mov     [rsp+108h+var_E8], eax
0x180004275  jmp     short loc_18000428C
0x180004277  xor     ebx, ebx
0x180004279  mov     [rsp+108h+var_E8], ebx
0x18000427d  mov     edi, [rsp+108h+arg_8]
0x180004284  mov     rsi, [rsp+108h+arg_0]
0x18000428c  test    ebx, ebx
0x18000428e  jz      loc_1800043B4
0x180004294  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000429c  mov     edx, edi; fdwReason
0x18000429e  mov     rcx, rsi; hinstDLL
0x1800042a1  call    DllMain
0x1800042a6  mov     ebx, eax
0x1800042a8  mov     [rsp+108h+var_E8], eax
0x1800042ac  jmp     short loc_1800042C3
0x1800042ae  xor     ebx, ebx
0x1800042b0  mov     [rsp+108h+var_E8], ebx
0x1800042b4  mov     edi, [rsp+108h+arg_8]
0x1800042bb  mov     rsi, [rsp+108h+arg_0]
0x1800042c3  cmp     edi, 1
0x1800042c6  jnz     short loc_18000433F
0x1800042c8  test    ebx, ebx
0x1800042ca  jnz     short loc_18000433F
0x1800042cc  xor     r8d, r8d; lpvReserved
0x1800042cf  xor     edx, edx; fdwReason
0x1800042d1  mov     rcx, rsi; hinstDLL
0x1800042d4  call    DllMain
0x1800042d9  jmp     short loc_1800042EE
0x1800042db  mov     edi, [rsp+108h+arg_8]
0x1800042e2  mov     rsi, [rsp+108h+arg_0]
0x1800042ea  mov     ebx, [rsp+108h+var_E8]
0x1800042ee  xor     r8d, r8d
0x1800042f1  xor     edx, edx
0x1800042f3  mov     rcx, rsi
0x1800042f6  call    _CRT_INIT
0x1800042fb  jmp     short loc_180004310
0x1800042fd  mov     edi, [rsp+108h+arg_8]
0x180004304  mov     rsi, [rsp+108h+arg_0]
0x18000430c  mov     ebx, [rsp+108h+var_E8]
0x180004310  mov     rax, cs:_pRawDllMain
0x180004317  test    rax, rax
0x18000431a  jz      short loc_18000433F
0x18000431c  xor     r8d, r8d
0x18000431f  xor     edx, edx
0x180004321  mov     rcx, rsi
0x180004324  call    cs:__guard_dispatch_icall_fptr
0x18000432a  jmp     short loc_18000433F
0x18000432c  mov     edi, [rsp+108h+arg_8]
0x180004333  mov     rsi, [rsp+108h+arg_0]
0x18000433b  mov     ebx, [rsp+108h+var_E8]
0x18000433f  test    edi, edi
0x180004341  jz      short loc_180004348
0x180004343  cmp     edi, 3
0x180004346  jnz     short loc_1800043B4
0x180004348  mov     r8, [rsp+108h+lpvReserved]
0x180004350  mov     edx, edi
0x180004352  mov     rcx, rsi
0x180004355  call    _CRT_INIT
0x18000435a  mov     ebx, eax
0x18000435c  mov     [rsp+108h+var_E8], eax
0x180004360  jmp     short loc_180004377
0x180004362  xor     ebx, ebx
0x180004364  mov     [rsp+108h+var_E8], ebx
0x180004368  mov     edi, [rsp+108h+arg_8]
0x18000436f  mov     rsi, [rsp+108h+arg_0]
0x180004377  mov     rax, cs:_pRawDllMain
0x18000437e  test    rax, rax
0x180004381  jz      short loc_1800043B4
0x180004383  cmp     cs:dword_18000F1C4, 0
0x18000438a  jz      short loc_1800043B4
0x18000438c  mov     r8, [rsp+108h+lpvReserved]
0x180004394  mov     edx, edi
0x180004396  mov     rcx, rsi
0x180004399  call    cs:__guard_dispatch_icall_fptr
0x18000439f  mov     ebx, eax
0x1800043a1  mov     [rsp+108h+var_E8], eax
0x1800043a5  jmp     short loc_1800043B4
0x1800043a7  xor     ebx, ebx
0x1800043a9  mov     [rsp+108h+var_E8], ebx
0x1800043ad  mov     edi, [rsp+108h+arg_8]
0x1800043b4  cmp     edi, 1
0x1800043b7  ja      short loc_1800043C3
0x1800043b9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800043c3  mov     eax, ebx
0x1800043c5  add     rsp, 0F0h
0x1800043cc  pop     rdi
0x1800043cd  pop     rsi
0x1800043ce  pop     rbx
0x1800043cf  retn
0x180009830  push    rbp
0x180009832  sub     rsp, 20h
0x180009836  mov     rbp, rdx
0x180009839  mov     rax, [rcx]
0x18000983c  mov     edx, [rax]
0x18000983e  mov     [rbp+0A8h], rcx
0x180009845  mov     [rbp+28h], edx
0x180009848  mov     eax, [rbp+28h]
0x18000984b  cmp     eax, 0E06D7363h
0x180009850  jnz     short loc_180009866
0x180009852  mov     rdx, [rbp+0A8h]
0x180009859  mov     ecx, [rbp+28h]
0x18000985c  call    _XcptFilter_0
0x180009861  mov     [rbp+30h], eax
0x180009864  jmp     short loc_18000986D
0x180009866  mov     dword ptr [rbp+30h], 0
0x18000986d  mov     eax, [rbp+30h]
0x180009870  add     rsp, 20h
0x180009874  pop     rbp
0x180009875  retn
0x180009877  push    rbp
0x180009879  sub     rsp, 20h
0x18000987d  mov     rbp, rdx
0x180009880  mov     rax, [rcx]
0x180009883  mov     edx, [rax]
0x180009885  mov     [rbp+0B0h], rcx
0x18000988c  mov     [rbp+38h], edx
0x18000988f  mov     eax, [rbp+38h]
0x180009892  cmp     eax, 0E06D7363h
0x180009897  jnz     short loc_1800098AD
0x180009899  mov     rdx, [rbp+0B0h]
0x1800098a0  mov     ecx, [rbp+38h]
0x1800098a3  call    _XcptFilter_0
0x1800098a8  mov     [rbp+40h], eax
0x1800098ab  jmp     short loc_1800098B4
0x1800098ad  mov     dword ptr [rbp+40h], 0
0x1800098b4  mov     eax, [rbp+40h]
0x1800098b7  add     rsp, 20h
0x1800098bb  pop     rbp
0x1800098bc  retn
0x1800098be  push    rbp
0x1800098c0  sub     rsp, 20h
0x1800098c4  mov     rbp, rdx
0x1800098c7  mov     rax, [rcx]
0x1800098ca  mov     edx, [rax]
0x1800098cc  mov     [rbp+0B8h], rcx
0x1800098d3  mov     [rbp+48h], edx
0x1800098d6  mov     eax, [rbp+48h]
0x1800098d9  cmp     eax, 0E06D7363h
0x1800098de  jnz     short loc_1800098F4
0x1800098e0  mov     rdx, [rbp+0B8h]
0x1800098e7  mov     ecx, [rbp+48h]
0x1800098ea  call    _XcptFilter_0
0x1800098ef  mov     [rbp+50h], eax
0x1800098f2  jmp     short loc_1800098FB
0x1800098f4  mov     dword ptr [rbp+50h], 0
0x1800098fb  mov     eax, [rbp+50h]
0x1800098fe  add     rsp, 20h
0x180009902  pop     rbp
0x180009903  retn
0x180009905  push    rbp
0x180009907  sub     rsp, 20h
0x18000990b  mov     rbp, rdx
0x18000990e  mov     rax, [rcx]
0x180009911  mov     edx, [rax]
0x180009913  mov     [rbp+0C0h], rcx
0x18000991a  mov     [rbp+58h], edx
0x18000991d  mov     eax, [rbp+58h]
0x180009920  cmp     eax, 0E06D7363h
0x180009925  jnz     short loc_18000993B
0x180009927  mov     rdx, [rbp+0C0h]
0x18000992e  mov     ecx, [rbp+58h]
0x180009931  call    _XcptFilter_0
0x180009936  mov     [rbp+60h], eax
0x180009939  jmp     short loc_180009942
0x18000993b  mov     dword ptr [rbp+60h], 0
0x180009942  mov     eax, [rbp+60h]
0x180009945  add     rsp, 20h
0x180009949  pop     rbp
0x18000994a  retn
0x18000994c  push    rbp
0x18000994e  sub     rsp, 20h
0x180009952  mov     rbp, rdx
0x180009955  mov     rax, [rcx]
0x180009958  mov     edx, [rax]
0x18000995a  mov     [rbp+0C8h], rcx
0x180009961  mov     [rbp+68h], edx
0x180009964  mov     eax, [rbp+68h]
0x180009967  cmp     eax, 0E06D7363h
0x18000996c  jnz     short loc_180009982
0x18000996e  mov     rdx, [rbp+0C8h]
0x180009975  mov     ecx, [rbp+68h]
0x180009978  call    _XcptFilter_0
0x18000997d  mov     [rbp+70h], eax
0x180009980  jmp     short loc_180009989
0x180009982  mov     dword ptr [rbp+70h], 0
0x180009989  mov     eax, [rbp+70h]
0x18000998c  add     rsp, 20h
0x180009990  pop     rbp
0x180009991  retn
0x180009993  push    rbp
0x180009995  sub     rsp, 20h
0x180009999  mov     rbp, rdx
0x18000999c  mov     rax, [rcx]
0x18000999f  mov     edx, [rax]
0x1800099a1  mov     [rbp+0D0h], rcx
0x1800099a8  mov     [rbp+78h], edx
0x1800099ab  mov     eax, [rbp+78h]
0x1800099ae  cmp     eax, 0E06D7363h
0x1800099b3  jnz     short loc_1800099CC
0x1800099b5  mov     rdx, [rbp+0D0h]
0x1800099bc  mov     ecx, [rbp+78h]
0x1800099bf  call    _XcptFilter_0
0x1800099c4  mov     [rbp+80h], eax
0x1800099ca  jmp     short loc_1800099D6
0x1800099cc  mov     dword ptr [rbp+80h], 0
0x1800099d6  mov     eax, [rbp+80h]
0x1800099dc  add     rsp, 20h
0x1800099e0  pop     rbp
0x1800099e1  retn
0x1800099e3  push    rbp
0x1800099e5  sub     rsp, 20h
0x1800099e9  mov     rbp, rdx
0x1800099ec  mov     rax, [rcx]
0x1800099ef  mov     edx, [rax]
0x1800099f1  mov     [rbp+0D8h], rcx
0x1800099f8  mov     [rbp+88h], edx
0x1800099fe  mov     eax, [rbp+88h]
0x180009a04  cmp     eax, 0E06D7363h
0x180009a09  jnz     short loc_180009A25
0x180009a0b  mov     rdx, [rbp+0D8h]
0x180009a12  mov     ecx, [rbp+88h]
0x180009a18  call    _XcptFilter_0
0x180009a1d  mov     [rbp+90h], eax
0x180009a23  jmp     short loc_180009A2F
0x180009a25  mov     dword ptr [rbp+90h], 0
0x180009a2f  mov     eax, [rbp+90h]
0x180009a35  add     rsp, 20h
0x180009a39  pop     rbp
0x180009a3a  retn
0x180009a3c  push    rbp
0x180009a3e  sub     rsp, 20h
0x180009a42  mov     rbp, rdx
0x180009a45  mov     rax, [rcx]
0x180009a48  mov     edx, [rax]
0x180009a4a  mov     [rbp+0E0h], rcx
0x180009a51  mov     [rbp+98h], edx
0x180009a57  mov     eax, [rbp+98h]
0x180009a5d  cmp     eax, 0E06D7363h
0x180009a62  jnz     short loc_180009A7E
0x180009a64  mov     rdx, [rbp+0E0h]
0x180009a6b  mov     ecx, [rbp+98h]
0x180009a71  call    _XcptFilter_0
0x180009a76  mov     [rbp+0A0h], eax
0x180009a7c  jmp     short loc_180009A88
0x180009a7e  mov     dword ptr [rbp+0A0h], 0
0x180009a88  mov     eax, [rbp+0A0h]
0x180009a8e  add     rsp, 20h
0x180009a92  pop     rbp
0x180009a93  retn
0x180009a95  push    rbp
0x180009a97  sub     rsp, 20h
0x180009a9b  mov     rbp, rdx
0x180009a9e  cmp     dword ptr [rbp+118h], 1
0x180009aa5  ja      short loc_180009AB1
0x180009aa7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
