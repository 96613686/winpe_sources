# MpObHandleOpenDesktopCallback

- ea: `0x14002e3c4`
- end: `0x14002e84d`
- name: `MpObHandleOpenDesktopCallback`
- size: `1161`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation`

## callers

- `0x14002e380`

## callees

- `0x1400018a4`
- `0x140003950`
- `0x1400049dc`
- `0x1400051bc`
- `0x14000dea8`
- `0x1400118d0`
- `0x140011900`
- `0x14002d340`
- `0x14002d430`
- `0x14002e3c4`
- `0x140030060`
- `0x140034b50`
- `0x140035080`
- `0x140035e50`
- `0x14003a1b0`
- `0x140056c20`
- `0x140066180`
- `0x140070414`

## import_xrefs

- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14002e59d`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14002e59d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002e5be`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002e5be`
- `ntoskrnl!IoGetCurrentProcess` at `0x14002e420`
- `ntoskrnl!IoGetCurrentProcess` at `0x14002e58e`
- `ntoskrnl!IoGetCurrentProcess` at `0x14002e420`
- `ntoskrnl!IoGetCurrentProcess` at `0x14002e58e`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14002e57d`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14002e7a2`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14002e57d`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14002e7a2`

## string_xrefs

- `0x14002e815`: `CreateHandle`

## pseudocode

```c
__int64 MpObHandleOpenDesktopCallback()
{
  __int64 result; // rax
  struct _KPROCESS *CurrentProcess; // rax

  result = MpData;
  if ( (*(_DWORD *)(MpData + 868) & 2) != 0 )
  {
    CurrentProcess = IoGetCurrentProcess();
    result = MpGetProcessContextByObject(CurrentProcess);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      result = HIDWORD(WPP_GLOBAL_Control->Timer);
      if ( (result & 4) != 0 )
        return WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_987d9fc7520d333ff9fdca1fa9c66d57_Traceguids);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14002e3c4  mov     [rsp-28h+arg_8], rbx
0x14002e3c9  mov     [rsp-28h+arg_10], rsi
0x14002e3ce  mov     [rsp-28h+arg_18], rdi
0x14002e3d3  push    rbp
0x14002e3d4  push    r12
0x14002e3d6  push    r13
0x14002e3d8  push    r14
0x14002e3da  push    r15
0x14002e3dc  mov     rbp, rsp
0x14002e3df  sub     rsp, 70h
0x14002e3e3  mov     rax, cs:__security_cookie
0x14002e3ea  xor     rax, rsp
0x14002e3ed  mov     [rbp+var_8], rax
0x14002e3f1  mov     rax, cs:MpData
0x14002e3f8  xor     r12d, r12d
0x14002e3fb  mov     [rbp+var_10], r12d
0x14002e3ff  mov     r14, rcx
0x14002e402  mov     [rbp+var_20], r12
0x14002e406  mov     esi, r12d
0x14002e409  mov     [rbp+var_30], r12
0x14002e40d  mov     edx, [rax+364h]
0x14002e413  mov     [rbp+var_28], r12
0x14002e417  mov     [rbp+var_18], r12
0x14002e41b  test    dl, 2
0x14002e41e  jz      short loc_14002E48F
0x14002e420  call    cs:__imp_IoGetCurrentProcess
0x14002e427  nop     dword ptr [rax+rax+00h]
0x14002e42c  mov     rcx, rax; Process
0x14002e42f  lea     rdx, [rbp+var_20]
0x14002e433  call    MpGetProcessContextByObject
0x14002e438  mov     rdi, [rbp+var_20]
0x14002e43c  test    rdi, rdi
0x14002e43f  jz      short loc_14002E4BA
0x14002e441  mov     ecx, [rdi+34h]
0x14002e444  test    cl, 8
0x14002e447  jz      short loc_14002E450
0x14002e449  bt      dword ptr [rdi+38h], 0Eh
0x14002e44e  jb      short loc_14002E4BA
0x14002e450  test    cl, 1
0x14002e453  jnz     loc_14002E4EB
0x14002e459  mov     eax, [rdi+38h]
0x14002e45c  test    al, 8
0x14002e45e  jz      loc_14002E4F8
0x14002e464  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e46b  lea     rbx, WPP_GLOBAL_Control
0x14002e472  cmp     rcx, rbx
0x14002e475  jz      short loc_14002E482
0x14002e477  mov     eax, [rcx+2Ch]
0x14002e47a  test    al, 4
0x14002e47c  jnz     loc_14002E6BE
0x14002e482  test    rdi, rdi
0x14002e485  jz      short loc_14002E48F
0x14002e487  mov     rcx, rdi
0x14002e48a  call    MpReleaseProcessContext
0x14002e48f  mov     rcx, [rbp+var_8]
0x14002e493  xor     rcx, rsp; StackCookie
0x14002e496  call    __security_check_cookie
0x14002e49b  lea     r11, [rsp+70h+var_s0]
0x14002e4a0  mov     rbx, [r11+38h]
0x14002e4a4  mov     rsi, [r11+40h]
0x14002e4a8  mov     rdi, [r11+48h]
0x14002e4ac  mov     rsp, r11
0x14002e4af  pop     r15
0x14002e4b1  pop     r14
0x14002e4b3  pop     r13
0x14002e4b5  pop     r12
0x14002e4b7  pop     rbp
0x14002e4b8  retn
0x14002e4ba  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e4c1  lea     rbx, WPP_GLOBAL_Control
0x14002e4c8  cmp     rcx, rbx
0x14002e4cb  jz      short loc_14002E482
0x14002e4cd  mov     eax, [rcx+2Ch]
0x14002e4d0  test    al, 4
0x14002e4d2  jz      short loc_14002E482
0x14002e4d4  mov     edx, 0Eh
0x14002e4d9  mov     rcx, [rcx+18h]
0x14002e4dd  lea     r8, WPP_987d9fc7520d333ff9fdca1fa9c66d57_Traceguids
0x14002e4e4  call    WPP_SF_
0x14002e4e9  jmp     short loc_14002E482
0x14002e4eb  bt      dword ptr [rdi+38h], 0Eh
0x14002e4f0  jb      loc_14002E459
0x14002e4f6  jmp     short loc_14002E4BA
0x14002e4f8  mov     rcx, [r14+8]; Object
0x14002e4fc  lea     rdx, [rbp+var_30]
0x14002e500  call    MpQueryObjectName
0x14002e505  mov     r15, [rbp+var_30]
0x14002e509  test    eax, eax
0x14002e50b  jnz     loc_14002E6C8
0x14002e511  movzx   ecx, word ptr [r15]
0x14002e515  test    cx, cx
0x14002e518  jz      loc_14002E651
0x14002e51e  mov     eax, [r14]
0x14002e521  cmp     eax, 1
0x14002e524  jnz     loc_14002E6B3
0x14002e52a  mov     rax, [r14+20h]
0x14002e52e  lea     r13d, [rcx+38h]
0x14002e532  mov     edx, r13d
0x14002e535  mov     [rbp+var_30], rax
0x14002e539  lea     rcx, [rbp+var_18]
0x14002e53d  call    MpAsyncCreateNotification
0x14002e542  mov     r12, [rbp+var_18]
0x14002e546  test    eax, eax
0x14002e548  js      loc_14002E674
0x14002e54e  lfence
0x14002e551  lea     r8, [rbp+var_10]
0x14002e555  call    MpQuerySessionId
0x14002e55a  lea     rbx, WPP_GLOBAL_Control
0x14002e561  test    eax, eax
0x14002e563  js      loc_14002E708
0x14002e569  xor     eax, eax
0x14002e56b  mov     [r12], rax
0x14002e56f  mov     [r12+8], r13d
0x14002e574  mov     dword ptr [r12+10h], 9
0x14002e57d  call    cs:__imp_PsGetCurrentProcessId
0x14002e584  nop     dword ptr [rax+rax+00h]
0x14002e589  mov     [r12+18h], eax
0x14002e58e  call    cs:__imp_IoGetCurrentProcess
0x14002e595  nop     dword ptr [rax+rax+00h]
0x14002e59a  mov     rcx, rax; Process
0x14002e59d  call    cs:__imp_PsGetProcessCreateTimeQuadPart
0x14002e5a4  nop     dword ptr [rax+rax+00h]
0x14002e5a9  mov     rcx, rax
0x14002e5ac  call    MpFileTimeToUlong64
0x14002e5b1  mov     [r12+1Ch], rax
0x14002e5b6  mov     eax, [rbp+var_10]
0x14002e5b9  mov     [r12+28h], eax
0x14002e5be  call    cs:__imp_PsGetCurrentThreadId
0x14002e5c5  nop     dword ptr [rax+rax+00h]
0x14002e5ca  mov     [r12+24h], eax
0x14002e5cf  lea     rcx, [r12+34h]; void *
0x14002e5d4  cmp     dword ptr [r14], 1
0x14002e5d8  setnz   al
0x14002e5db  mov     [r12+2Ch], al
0x14002e5e0  mov     al, [r14+4]
0x14002e5e4  and     al, 1
0x14002e5e6  mov     [r12+2Dh], al
0x14002e5eb  mov     rax, [rbp+var_30]
0x14002e5ef  mov     eax, [rax]
0x14002e5f1  mov     [r12+30h], eax
0x14002e5f6  movzx   r8d, word ptr [r15]; Size
0x14002e5fa  mov     rdx, [r15+8]; Src
0x14002e5fe  call    memmove
0x14002e603  movzx   eax, word ptr [r15]
0x14002e607  xor     ecx, ecx
0x14002e609  shr     rax, 1
0x14002e60c  xor     r8d, r8d
0x14002e60f  mov     edx, r13d
0x14002e612  mov     [rsp+70h+var_50], rdi
0x14002e617  lea     r9d, [rcx+1]
0x14002e61b  mov     [r12+rax*2+34h], cx
0x14002e621  mov     rcx, r12
0x14002e624  call    MpAsyncSendNotification
0x14002e629  test    eax, eax
0x14002e62b  js      loc_14002E755
0x14002e631  mov     rax, cs:WPP_GLOBAL_Control
0x14002e638  mov     ecx, [rax+2Ch]
0x14002e63b  test    cl, 4
0x14002e63e  jnz     loc_14002E7A2
0x14002e644  test    r12, r12
0x14002e647  jz      short loc_14002E651
0x14002e649  mov     rcx, r12
0x14002e64c  call    MpAsyncDereferenceNotification
0x14002e651  test    r15, r15
0x14002e654  jz      short loc_14002E65E
0x14002e656  mov     rcx, r15
0x14002e659  call    MpFreeObjectName
0x14002e65e  test    rsi, rsi
0x14002e661  jz      loc_14002E482
0x14002e667  mov     rcx, rsi
0x14002e66a  call    MpFreeString
0x14002e66f  jmp     loc_14002E482
0x14002e674  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e67b  lea     rbx, WPP_GLOBAL_Control
0x14002e682  cmp     rcx, rbx
0x14002e685  jz      short loc_14002E644
0x14002e687  mov     ecx, [rcx+2Ch]
0x14002e68a  test    cl, 1
0x14002e68d  jz      short loc_14002E644
0x14002e68f  lfence
0x14002e692  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e699  lea     r8, WPP_987d9fc7520d333ff9fdca1fa9c66d57_Traceguids
0x14002e6a0  mov     edx, 11h
0x14002e6a5  mov     r9d, eax
0x14002e6a8  mov     rcx, [rcx+18h]
0x14002e6ac  call    WPP_SF_d
0x14002e6b1  jmp     short loc_14002E644
0x14002e6b3  cmp     eax, 2
0x14002e6b6  jz      loc_14002E52A
0x14002e6bc  jmp     short loc_14002E651
0x14002e6be  mov     edx, 0Fh
0x14002e6c3  jmp     loc_14002E4D9
0x14002e6c8  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e6cf  lea     rbx, WPP_GLOBAL_Control
0x14002e6d6  cmp     rcx, rbx
0x14002e6d9  jz      loc_14002E651
0x14002e6df  mov     edx, [rcx+2Ch]
0x14002e6e2  test    dl, 1
0x14002e6e5  jz      loc_14002E651
0x14002e6eb  mov     rcx, [rcx+18h]
0x14002e6ef  lea     r8, WPP_987d9fc7520d333ff9fdca1fa9c66d57_Traceguids
0x14002e6f6  mov     edx, 10h
0x14002e6fb  mov     r9d, eax
0x14002e6fe  call    WPP_SF_d
0x14002e703  jmp     loc_14002E651
0x14002e708  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e70f  cmp     rcx, rbx
0x14002e712  jz      loc_14002E569
0x14002e718  mov     ecx, [rcx+2Ch]
0x14002e71b  test    cl, 1
0x14002e71e  jz      loc_14002E569
0x14002e724  lfence
0x14002e727  mov     r9, gs:188h
0x14002e730  lea     r8, WPP_987d9fc7520d333ff9fdca1fa9c66d57_Traceguids
0x14002e737  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e73e  mov     edx, 12h
0x14002e743  mov     dword ptr [rsp+70h+var_50], eax
0x14002e747  mov     rcx, [rcx+18h]
0x14002e74b  call    WPP_SF_qD
0x14002e750  jmp     loc_14002E569
0x14002e755  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e75c  cmp     rcx, rbx
0x14002e75f  jz      loc_14002E644
0x14002e765  mov     ecx, [rcx+2Ch]
0x14002e768  test    cl, 1
0x14002e76b  jz      loc_14002E644
0x14002e771  lfence
0x14002e774  mov     r9, gs:188h
0x14002e77d  lea     r8, WPP_987d9fc7520d333ff9fdca1fa9c66d57_Traceguids
0x14002e784  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e78b  mov     edx, 13h
0x14002e790  mov     dword ptr [rsp+70h+var_50], eax
0x14002e794  mov     rcx, [rcx+18h]
0x14002e798  call    WPP_SF_qD
0x14002e79d  jmp     loc_14002E644
0x14002e7a2  call    cs:__imp_PsGetCurrentProcessId
0x14002e7a9  nop     dword ptr [rax+rax+00h]
0x14002e7ae  mov     rcx, rax
0x14002e7b1  lea     rdx, [rbp+var_28]
0x14002e7b5  call    MpGetProcessName
0x14002e7ba  test    eax, eax
0x14002e7bc  jz      short loc_14002E7F3
0x14002e7be  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e7c5  cmp     rcx, rbx
0x14002e7c8  jz      short loc_14002E7EA
0x14002e7ca  mov     edx, [rcx+2Ch]
0x14002e7cd  test    dl, 1
0x14002e7d0  jz      short loc_14002E7EA
0x14002e7d2  mov     rcx, [rcx+18h]
0x14002e7d6  lea     r8, WPP_987d9fc7520d333ff9fdca1fa9c66d57_Traceguids
0x14002e7dd  mov     edx, 14h
0x14002e7e2  mov     r9d, eax
0x14002e7e5  call    WPP_SF_d
0x14002e7ea  mov     rsi, [rbp+var_28]
0x14002e7ee  jmp     loc_14002E644
0x14002e7f3  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e7fa  cmp     rcx, rbx
0x14002e7fd  jz      short loc_14002E7EA
0x14002e7ff  mov     eax, [rcx+2Ch]
0x14002e802  test    al, 4
0x14002e804  jz      short loc_14002E7EA
0x14002e806  mov     rax, [rbp+var_30]
0x14002e80a  lea     r8, aDuplicatehandl
0x14002e811  mov     edx, [r14+4]
0x14002e815  lea     r9, aCreatehandle
0x14002e81c  mov     rsi, [rbp+var_28]
0x14002e820  and     edx, 1
0x14002e823  cmp     dword ptr [r14], 1
0x14002e827  mov     eax, [rax]
0x14002e829  mov     rcx, [rcx+18h]
0x14002e82d  cmovnz  r9, r8
0x14002e831  mov     [rsp+70h+var_38], eax
0x14002e835  mov     [rsp+70h+var_40], edx
0x14002e839  mov     [rsp+70h+var_48], rsi
0x14002e83e  mov     [rsp+70h+var_50], r15
0x14002e843  call    WPP_SF_SZZdD
0x14002e848  jmp     loc_14002E644
```
