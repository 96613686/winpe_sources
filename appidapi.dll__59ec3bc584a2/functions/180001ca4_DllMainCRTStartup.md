# __DllMainCRTStartup

- ea: `0x180001ca4`
- end: `0x180001eb0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001c60`

## callees

- `0x180001a30`
- `0x180001ca4`
- `0x180002397`
- `0x180002f50`
- `0x180009600`

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
  if ( (_DWORD)fdwReason || dword_1800101C0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800101C4 = 1;
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
            if ( dword_1800101C4 )
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
0x180001ca4  mov     [rsp+lpvReserved], r8
0x180001ca9  mov     [rsp+arg_8], edx
0x180001cad  mov     [rsp+arg_0], rcx
0x180001cb2  push    rbx
0x180001cb3  push    rsi
0x180001cb4  push    rdi
0x180001cb5  sub     rsp, 0F0h
0x180001cbc  mov     edi, edx
0x180001cbe  mov     rsi, rcx
0x180001cc1  mov     ebx, 1
0x180001cc6  cmp     edx, ebx
0x180001cc8  ja      short loc_180001CD0
0x180001cca  mov     cs:__native_dllmain_reason, edx
0x180001cd0  test    edx, edx
0x180001cd2  jnz     short loc_180001CE7
0x180001cd4  cmp     cs:dword_1800101C0, edx
0x180001cda  jnz     short loc_180001CE7
0x180001cdc  xor     ebx, ebx
0x180001cde  mov     [rsp+108h+var_E8], ebx
0x180001ce2  jmp     loc_180001E94
0x180001ce7  lea     eax, [rdx-1]
0x180001cea  cmp     eax, 1
0x180001ced  ja      loc_180001D74
0x180001cf3  mov     rax, cs:_pRawDllMain
0x180001cfa  test    rax, rax
0x180001cfd  jz      short loc_180001D35
0x180001cff  cmp     edx, 1
0x180001d02  jnz     short loc_180001D0A
0x180001d04  mov     cs:dword_1800101C4, edx
0x180001d0a  mov     r8, [rsp+108h+lpvReserved]
0x180001d12  call    cs:__guard_dispatch_icall_fptr
0x180001d18  mov     ebx, eax
0x180001d1a  mov     [rsp+108h+var_E8], eax
0x180001d1e  jmp     short loc_180001D35
0x180001d20  xor     ebx, ebx
0x180001d22  mov     [rsp+108h+var_E8], ebx
0x180001d26  mov     edi, [rsp+108h+arg_8]
0x180001d2d  mov     rsi, [rsp+108h+arg_0]
0x180001d35  test    ebx, ebx
0x180001d37  jz      loc_180001E94
0x180001d3d  mov     r8, [rsp+108h+lpvReserved]
0x180001d45  mov     edx, edi
0x180001d47  mov     rcx, rsi
0x180001d4a  call    _CRT_INIT
0x180001d4f  mov     ebx, eax
0x180001d51  mov     [rsp+108h+var_E8], eax
0x180001d55  jmp     short loc_180001D6C
0x180001d57  xor     ebx, ebx
0x180001d59  mov     [rsp+108h+var_E8], ebx
0x180001d5d  mov     edi, [rsp+108h+arg_8]
0x180001d64  mov     rsi, [rsp+108h+arg_0]
0x180001d6c  test    ebx, ebx
0x180001d6e  jz      loc_180001E94
0x180001d74  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180001d7c  mov     edx, edi; fdwReason
0x180001d7e  mov     rcx, rsi; hinstDLL
0x180001d81  call    DllMain
0x180001d86  mov     ebx, eax
0x180001d88  mov     [rsp+108h+var_E8], eax
0x180001d8c  jmp     short loc_180001DA3
0x180001d8e  xor     ebx, ebx
0x180001d90  mov     [rsp+108h+var_E8], ebx
0x180001d94  mov     edi, [rsp+108h+arg_8]
0x180001d9b  mov     rsi, [rsp+108h+arg_0]
0x180001da3  cmp     edi, 1
0x180001da6  jnz     short loc_180001E1F
0x180001da8  test    ebx, ebx
0x180001daa  jnz     short loc_180001E1F
0x180001dac  xor     r8d, r8d; lpvReserved
0x180001daf  xor     edx, edx; fdwReason
0x180001db1  mov     rcx, rsi; hinstDLL
0x180001db4  call    DllMain
0x180001db9  jmp     short loc_180001DCE
0x180001dbb  mov     edi, [rsp+108h+arg_8]
0x180001dc2  mov     rsi, [rsp+108h+arg_0]
0x180001dca  mov     ebx, [rsp+108h+var_E8]
0x180001dce  xor     r8d, r8d
0x180001dd1  xor     edx, edx
0x180001dd3  mov     rcx, rsi
0x180001dd6  call    _CRT_INIT
0x180001ddb  jmp     short loc_180001DF0
0x180001ddd  mov     edi, [rsp+108h+arg_8]
0x180001de4  mov     rsi, [rsp+108h+arg_0]
0x180001dec  mov     ebx, [rsp+108h+var_E8]
0x180001df0  mov     rax, cs:_pRawDllMain
0x180001df7  test    rax, rax
0x180001dfa  jz      short loc_180001E1F
0x180001dfc  xor     r8d, r8d
0x180001dff  xor     edx, edx
0x180001e01  mov     rcx, rsi
0x180001e04  call    cs:__guard_dispatch_icall_fptr
0x180001e0a  jmp     short loc_180001E1F
0x180001e0c  mov     edi, [rsp+108h+arg_8]
0x180001e13  mov     rsi, [rsp+108h+arg_0]
0x180001e1b  mov     ebx, [rsp+108h+var_E8]
0x180001e1f  test    edi, edi
0x180001e21  jz      short loc_180001E28
0x180001e23  cmp     edi, 3
0x180001e26  jnz     short loc_180001E94
0x180001e28  mov     r8, [rsp+108h+lpvReserved]
0x180001e30  mov     edx, edi
0x180001e32  mov     rcx, rsi
0x180001e35  call    _CRT_INIT
0x180001e3a  mov     ebx, eax
0x180001e3c  mov     [rsp+108h+var_E8], eax
0x180001e40  jmp     short loc_180001E57
0x180001e42  xor     ebx, ebx
0x180001e44  mov     [rsp+108h+var_E8], ebx
0x180001e48  mov     edi, [rsp+108h+arg_8]
0x180001e4f  mov     rsi, [rsp+108h+arg_0]
0x180001e57  mov     rax, cs:_pRawDllMain
0x180001e5e  test    rax, rax
0x180001e61  jz      short loc_180001E94
0x180001e63  cmp     cs:dword_1800101C4, 0
0x180001e6a  jz      short loc_180001E94
0x180001e6c  mov     r8, [rsp+108h+lpvReserved]
0x180001e74  mov     edx, edi
0x180001e76  mov     rcx, rsi
0x180001e79  call    cs:__guard_dispatch_icall_fptr
0x180001e7f  mov     ebx, eax
0x180001e81  mov     [rsp+108h+var_E8], eax
0x180001e85  jmp     short loc_180001E94
0x180001e87  xor     ebx, ebx
0x180001e89  mov     [rsp+108h+var_E8], ebx
0x180001e8d  mov     edi, [rsp+108h+arg_8]
0x180001e94  cmp     edi, 1
0x180001e97  ja      short loc_180001EA3
0x180001e99  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001ea3  mov     eax, ebx
0x180001ea5  add     rsp, 0F0h
0x180001eac  pop     rdi
0x180001ead  pop     rsi
0x180001eae  pop     rbx
0x180001eaf  retn
0x180009727  push    rbp
0x180009729  sub     rsp, 20h
0x18000972d  mov     rbp, rdx
0x180009730  mov     rax, [rcx]
0x180009733  mov     edx, [rax]
0x180009735  mov     [rbp+0A8h], rcx
0x18000973c  mov     [rbp+28h], edx
0x18000973f  mov     eax, [rbp+28h]
0x180009742  cmp     eax, 0E06D7363h
0x180009747  jnz     short loc_18000975D
0x180009749  mov     rdx, [rbp+0A8h]
0x180009750  mov     ecx, [rbp+28h]
0x180009753  call    _XcptFilter_0
0x180009758  mov     [rbp+30h], eax
0x18000975b  jmp     short loc_180009764
0x18000975d  mov     dword ptr [rbp+30h], 0
0x180009764  mov     eax, [rbp+30h]
0x180009767  add     rsp, 20h
0x18000976b  pop     rbp
0x18000976c  retn
0x18000976e  push    rbp
0x180009770  sub     rsp, 20h
0x180009774  mov     rbp, rdx
0x180009777  mov     rax, [rcx]
0x18000977a  mov     edx, [rax]
0x18000977c  mov     [rbp+0B0h], rcx
0x180009783  mov     [rbp+38h], edx
0x180009786  mov     eax, [rbp+38h]
0x180009789  cmp     eax, 0E06D7363h
0x18000978e  jnz     short loc_1800097A4
0x180009790  mov     rdx, [rbp+0B0h]
0x180009797  mov     ecx, [rbp+38h]
0x18000979a  call    _XcptFilter_0
0x18000979f  mov     [rbp+40h], eax
0x1800097a2  jmp     short loc_1800097AB
0x1800097a4  mov     dword ptr [rbp+40h], 0
0x1800097ab  mov     eax, [rbp+40h]
0x1800097ae  add     rsp, 20h
0x1800097b2  pop     rbp
0x1800097b3  retn
0x1800097b5  push    rbp
0x1800097b7  sub     rsp, 20h
0x1800097bb  mov     rbp, rdx
0x1800097be  mov     rax, [rcx]
0x1800097c1  mov     edx, [rax]
0x1800097c3  mov     [rbp+0B8h], rcx
0x1800097ca  mov     [rbp+48h], edx
0x1800097cd  mov     eax, [rbp+48h]
0x1800097d0  cmp     eax, 0E06D7363h
0x1800097d5  jnz     short loc_1800097EB
0x1800097d7  mov     rdx, [rbp+0B8h]
0x1800097de  mov     ecx, [rbp+48h]
0x1800097e1  call    _XcptFilter_0
0x1800097e6  mov     [rbp+50h], eax
0x1800097e9  jmp     short loc_1800097F2
0x1800097eb  mov     dword ptr [rbp+50h], 0
0x1800097f2  mov     eax, [rbp+50h]
0x1800097f5  add     rsp, 20h
0x1800097f9  pop     rbp
0x1800097fa  retn
0x1800097fc  push    rbp
0x1800097fe  sub     rsp, 20h
0x180009802  mov     rbp, rdx
0x180009805  mov     rax, [rcx]
0x180009808  mov     edx, [rax]
0x18000980a  mov     [rbp+0C0h], rcx
0x180009811  mov     [rbp+58h], edx
0x180009814  mov     eax, [rbp+58h]
0x180009817  cmp     eax, 0E06D7363h
0x18000981c  jnz     short loc_180009832
0x18000981e  mov     rdx, [rbp+0C0h]
0x180009825  mov     ecx, [rbp+58h]
0x180009828  call    _XcptFilter_0
0x18000982d  mov     [rbp+60h], eax
0x180009830  jmp     short loc_180009839
0x180009832  mov     dword ptr [rbp+60h], 0
0x180009839  mov     eax, [rbp+60h]
0x18000983c  add     rsp, 20h
0x180009840  pop     rbp
0x180009841  retn
0x180009843  push    rbp
0x180009845  sub     rsp, 20h
0x180009849  mov     rbp, rdx
0x18000984c  mov     rax, [rcx]
0x18000984f  mov     edx, [rax]
0x180009851  mov     [rbp+0C8h], rcx
0x180009858  mov     [rbp+68h], edx
0x18000985b  mov     eax, [rbp+68h]
0x18000985e  cmp     eax, 0E06D7363h
0x180009863  jnz     short loc_180009879
0x180009865  mov     rdx, [rbp+0C8h]
0x18000986c  mov     ecx, [rbp+68h]
0x18000986f  call    _XcptFilter_0
0x180009874  mov     [rbp+70h], eax
0x180009877  jmp     short loc_180009880
0x180009879  mov     dword ptr [rbp+70h], 0
0x180009880  mov     eax, [rbp+70h]
0x180009883  add     rsp, 20h
0x180009887  pop     rbp
0x180009888  retn
0x18000988a  push    rbp
0x18000988c  sub     rsp, 20h
0x180009890  mov     rbp, rdx
0x180009893  mov     rax, [rcx]
0x180009896  mov     edx, [rax]
0x180009898  mov     [rbp+0D0h], rcx
0x18000989f  mov     [rbp+78h], edx
0x1800098a2  mov     eax, [rbp+78h]
0x1800098a5  cmp     eax, 0E06D7363h
0x1800098aa  jnz     short loc_1800098C3
0x1800098ac  mov     rdx, [rbp+0D0h]
0x1800098b3  mov     ecx, [rbp+78h]
0x1800098b6  call    _XcptFilter_0
0x1800098bb  mov     [rbp+80h], eax
0x1800098c1  jmp     short loc_1800098CD
0x1800098c3  mov     dword ptr [rbp+80h], 0
0x1800098cd  mov     eax, [rbp+80h]
0x1800098d3  add     rsp, 20h
0x1800098d7  pop     rbp
0x1800098d8  retn
0x1800098da  push    rbp
0x1800098dc  sub     rsp, 20h
0x1800098e0  mov     rbp, rdx
0x1800098e3  mov     rax, [rcx]
0x1800098e6  mov     edx, [rax]
0x1800098e8  mov     [rbp+0D8h], rcx
0x1800098ef  mov     [rbp+88h], edx
0x1800098f5  mov     eax, [rbp+88h]
0x1800098fb  cmp     eax, 0E06D7363h
0x180009900  jnz     short loc_18000991C
0x180009902  mov     rdx, [rbp+0D8h]
0x180009909  mov     ecx, [rbp+88h]
0x18000990f  call    _XcptFilter_0
0x180009914  mov     [rbp+90h], eax
0x18000991a  jmp     short loc_180009926
0x18000991c  mov     dword ptr [rbp+90h], 0
0x180009926  mov     eax, [rbp+90h]
0x18000992c  add     rsp, 20h
0x180009930  pop     rbp
0x180009931  retn
0x180009933  push    rbp
0x180009935  sub     rsp, 20h
0x180009939  mov     rbp, rdx
0x18000993c  mov     rax, [rcx]
0x18000993f  mov     edx, [rax]
0x180009941  mov     [rbp+0E0h], rcx
0x180009948  mov     [rbp+98h], edx
0x18000994e  mov     eax, [rbp+98h]
0x180009954  cmp     eax, 0E06D7363h
0x180009959  jnz     short loc_180009975
0x18000995b  mov     rdx, [rbp+0E0h]
0x180009962  mov     ecx, [rbp+98h]
0x180009968  call    _XcptFilter_0
0x18000996d  mov     [rbp+0A0h], eax
0x180009973  jmp     short loc_18000997F
0x180009975  mov     dword ptr [rbp+0A0h], 0
0x18000997f  mov     eax, [rbp+0A0h]
0x180009985  add     rsp, 20h
0x180009989  pop     rbp
0x18000998a  retn
0x18000998c  push    rbp
0x18000998e  sub     rsp, 20h
0x180009992  mov     rbp, rdx
0x180009995  cmp     dword ptr [rbp+118h], 1
0x18000999c  ja      short loc_1800099A8
0x18000999e  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
