# Endpoint_EndpointStaticStreamsEnableCompletion

- ea: `0x140047b60`
- end: `0x140047dc9`
- name: `Endpoint_EndpointStaticStreamsEnableCompletion`
- size: `617`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x1400038c0`
- `0x14002792c`
- `0x140029aac`
- `0x14004560c`
- `0x140047240`
- `0x140047b60`
- `0x140059970`
- `0x1400599b0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140047c51`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047c51`

## pseudocode

```c
__int64 __fastcall Endpoint_EndpointStaticStreamsEnableCompletion(__int64 a1, int a2)
{
  __int16 v4; // ax
  __int64 v5; // r14
  __int64 **v6; // rax
  __int64 v7; // rdx
  __int64 *v8; // rdi
  __int64 v9; // rbx
  int v10; // edx
  unsigned int i; // esi
  int v12; // edx
  _OWORD v14[2]; // [rsp+50h] [rbp-58h] BYREF
  __int64 v15; // [rsp+70h] [rbp-38h]

  v15 = 0;
  memset(v14, 0, sizeof(v14));
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount > 0x33 )
    {
      LOWORD(v14[0]) = *(_WORD *)(WdfStructures + 408);
      goto LABEL_7;
    }
    v4 = -1;
  }
  else
  {
    v4 = 40;
  }
  LOWORD(v14[0]) = v4;
LABEL_7:
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _OWORD *))(WdfFunctions_01033 + 2128))(
    WdfDriverGlobals,
    a1,
    v14);
  v5 = *((_QWORD *)&v14[0] + 1);
  v6 = (__int64 **)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
                     WdfDriverGlobals,
                     a1,
                     off_14006BF00);
  v8 = *v6;
  v9 = **v6;
  if ( a2 < 0 )
  {
    for ( i = 1; i <= *((_DWORD *)v8 + 2); ++i )
    {
      LOBYTE(v7) = 1;
      TR_Disable_Internal(v8[13 * i - 7], v7);
    }
    XilEndpoint_FreeStreamContextArray(v8);
    *(_QWORD *)(v9 + 144) = *(_QWORD *)(v9 + 136);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = 2;
      WPP_RECORDER_SF_dddd(
        *(_QWORD *)(v9 + 80),
        v12,
        13,
        117,
        (__int64)WPP_efed3b2fad403e600dcc20c948898b03_Traceguids,
        *(_BYTE *)(*(_QWORD *)(v9 + 16) + 143LL),
        *(_DWORD *)(v9 + 152),
        *((_DWORD *)v8 + 2),
        a2);
    }
    *(_DWORD *)(v5 + 4) = -2147481600;
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01033 + 1232))(
      WdfDriverGlobals,
      *(_QWORD *)(*(_QWORD *)(v9 + 88) + 72LL));
  }
  else
  {
    LOBYTE(v7) = 1;
    TR_Disable_Internal(*(_QWORD *)(v9 + 88), v7);
    XilEndpoint_FreeStreamContextArray(*(_QWORD *)(v9 + 136));
    ExFreePoolWithTag(*(PVOID *)(v9 + 136), 0x49434858u);
    *(_QWORD *)(v9 + 136) = 0;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v10 = *(unsigned __int8 *)(*(_QWORD *)(v9 + 16) + 143LL);
      LOBYTE(v10) = 4;
      WPP_RECORDER_SF_ddd(
        *(_QWORD *)(v9 + 80),
        v10,
        13,
        116,
        (__int64)WPP_efed3b2fad403e600dcc20c948898b03_Traceguids,
        *(_BYTE *)(*(_QWORD *)(v9 + 16) + 143LL),
        *(_DWORD *)(v9 + 152),
        *((_DWORD *)v8 + 2));
    }
    *(_DWORD *)(v5 + 4) = 0;
    ESM_AddEsmEvent(v9, 146);
  }
  return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01033 + 2104))(
           WdfDriverGlobals,
           a1,
           (unsigned int)a2);
}

```

## disassembly

```asm
0x140047b60  mov     [rsp+arg_10], rbx
0x140047b65  push    rbp
0x140047b66  push    rsi
0x140047b67  push    rdi
0x140047b68  push    r14
0x140047b6a  push    r15
0x140047b6c  sub     rsp, 80h
0x140047b73  mov     rax, cs:__security_cookie
0x140047b7a  xor     rax, rsp
0x140047b7d  mov     [rsp+0A8h+var_30], rax
0x140047b82  xor     eax, eax
0x140047b84  xorps   xmm0, xmm0
0x140047b87  xor     esi, esi
0x140047b89  mov     [rsp+0A8h+var_38], rax
0x140047b8e  cmp     cs:WdfClientVersionHigherThanFramework, sil
0x140047b95  mov     ebp, edx
0x140047b97  mov     r15, rcx
0x140047b9a  movups  [rsp+0A8h+var_58], xmm0
0x140047b9f  movups  [rsp+0A8h+var_48], xmm0
0x140047ba4  jz      short loc_140047BCB
0x140047ba6  cmp     cs:WdfStructureCount, 33h ; '3'
0x140047bad  jbe     short loc_140047BC4
0x140047baf  mov     rax, cs:WdfStructures
0x140047bb6  movzx   ecx, word ptr [rax+198h]
0x140047bbd  mov     word ptr [rsp+0A8h+var_58], cx
0x140047bc2  jmp     short loc_140047BD5
0x140047bc4  mov     eax, 0FFFFh
0x140047bc9  jmp     short loc_140047BD0
0x140047bcb  mov     eax, 28h ; '('
0x140047bd0  mov     word ptr [rsp+0A8h+var_58], ax
0x140047bd5  mov     rax, cs:WdfFunctions_01033
0x140047bdc  lea     r8, [rsp+0A8h+var_58]
0x140047be1  mov     rcx, cs:WdfDriverGlobals
0x140047be8  mov     rdx, r15
0x140047beb  mov     rax, [rax+850h]
0x140047bf2  call    _guard_dispatch_icall
0x140047bf7  mov     rax, cs:WdfFunctions_01033
0x140047bfe  mov     rdx, r15
0x140047c01  mov     r8, cs:off_14006BF00
0x140047c08  mov     rcx, cs:WdfDriverGlobals
0x140047c0f  mov     r14, qword ptr [rsp+0A8h+var_58+8]
0x140047c14  mov     rax, [rax+650h]
0x140047c1b  call    _guard_dispatch_icall
0x140047c20  mov     rdi, [rax]
0x140047c23  mov     rbx, [rdi]
0x140047c26  test    ebp, ebp
0x140047c28  js      loc_140047CCB
0x140047c2e  mov     rcx, [rbx+58h]
0x140047c32  mov     dl, 1
0x140047c34  call    TR_Disable_Internal
0x140047c39  mov     rcx, [rbx+88h]
0x140047c40  call    XilEndpoint_FreeStreamContextArray
0x140047c45  mov     rcx, [rbx+88h]; P
0x140047c4c  mov     edx, 49434858h; Tag
0x140047c51  call    cs:__imp_ExFreePoolWithTag
0x140047c58  nop     dword ptr [rax+rax+00h]
0x140047c5d  mov     [rbx+88h], rsi
0x140047c64  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140047c6b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140047c72  jz      short loc_140047CB5
0x140047c74  mov     rax, [rbx+10h]
0x140047c78  mov     r9d, 74h ; 't'
0x140047c7e  mov     rcx, [rbx+50h]
0x140047c82  movzx   edx, byte ptr [rax+8Fh]
0x140047c89  lea     r8d, [r9-67h]
0x140047c8d  mov     eax, [rdi+8]
0x140047c90  mov     [rsp+0A8h+var_70], eax
0x140047c94  mov     eax, [rbx+98h]
0x140047c9a  mov     [rsp+0A8h+var_78], eax
0x140047c9e  lea     rax, WPP_efed3b2fad403e600dcc20c948898b03_Traceguids
0x140047ca5  mov     [rsp+0A8h+var_80], edx
0x140047ca9  mov     dl, 4
0x140047cab  mov     [rsp+0A8h+var_88], rax
0x140047cb0  call    WPP_RECORDER_SF_ddd
0x140047cb5  mov     edx, 92h
0x140047cba  mov     [r14+4], esi
0x140047cbe  mov     rcx, rbx
0x140047cc1  call    ESM_AddEsmEvent
0x140047cc6  jmp     loc_140047D84
0x140047ccb  mov     esi, 1
0x140047cd0  cmp     [rdi+8], esi
0x140047cd3  jb      short loc_140047CEF
0x140047cd5  lea     ecx, [rsi-1]
0x140047cd8  mov     dl, 1
0x140047cda  imul    rcx, 68h ; 'h'
0x140047cde  mov     rcx, [rcx+rdi+30h]
0x140047ce3  call    TR_Disable_Internal
0x140047ce8  inc     esi
0x140047cea  cmp     esi, [rdi+8]
0x140047ced  jbe     short loc_140047CD5
0x140047cef  mov     rcx, rdi
0x140047cf2  call    XilEndpoint_FreeStreamContextArray
0x140047cf7  mov     rax, [rbx+88h]
0x140047cfe  mov     [rbx+90h], rax
0x140047d05  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140047d0c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140047d13  jz      short loc_140047D5A
0x140047d15  mov     rax, [rbx+10h]
0x140047d19  mov     r9d, 75h ; 'u'
0x140047d1f  mov     [rsp+0A8h+var_68], ebp
0x140047d23  mov     dl, 2
0x140047d25  movzx   ecx, byte ptr [rax+8Fh]
0x140047d2c  lea     r8d, [r9-68h]
0x140047d30  mov     eax, [rdi+8]
0x140047d33  mov     [rsp+0A8h+var_70], eax
0x140047d37  mov     eax, [rbx+98h]
0x140047d3d  mov     [rsp+0A8h+var_78], eax
0x140047d41  lea     rax, WPP_efed3b2fad403e600dcc20c948898b03_Traceguids
0x140047d48  mov     [rsp+0A8h+var_80], ecx
0x140047d4c  mov     rcx, [rbx+50h]
0x140047d50  mov     [rsp+0A8h+var_88], rax
0x140047d55  call    WPP_RECORDER_SF_dddd
0x140047d5a  mov     dword ptr [r14+4], 80000800h
0x140047d62  mov     rdx, [rbx+58h]
0x140047d66  mov     rax, cs:WdfFunctions_01033
0x140047d6d  mov     rcx, cs:WdfDriverGlobals
0x140047d74  mov     rdx, [rdx+48h]
0x140047d78  mov     rax, [rax+4D0h]
0x140047d7f  call    _guard_dispatch_icall
0x140047d84  mov     rax, cs:WdfFunctions_01033
0x140047d8b  mov     r8d, ebp
0x140047d8e  mov     rcx, cs:WdfDriverGlobals
0x140047d95  mov     rdx, r15
0x140047d98  mov     rax, [rax+838h]
0x140047d9f  call    _guard_dispatch_icall
0x140047da4  mov     rcx, [rsp+0A8h+var_30]
0x140047da9  xor     rcx, rsp; StackCookie
0x140047dac  call    __security_check_cookie
0x140047db1  mov     rbx, [rsp+0A8h+arg_10]
0x140047db9  add     rsp, 80h
0x140047dc0  pop     r15
0x140047dc2  pop     r14
0x140047dc4  pop     rdi
0x140047dc5  pop     rsi
0x140047dc6  pop     rbp
0x140047dc7  retn
```
