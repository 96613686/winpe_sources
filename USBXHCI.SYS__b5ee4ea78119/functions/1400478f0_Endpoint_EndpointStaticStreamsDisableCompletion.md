# Endpoint_EndpointStaticStreamsDisableCompletion

- ea: `0x1400478f0`
- end: `0x140047b4b`
- name: `Endpoint_EndpointStaticStreamsDisableCompletion`
- size: `603`
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
- `0x1400478f0`
- `0x140059970`
- `0x1400599b0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140047a80`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047a80`

## pseudocode

```c
__int64 __fastcall Endpoint_EndpointStaticStreamsDisableCompletion(__int64 a1, int a2)
{
  __int16 v4; // ax
  __int64 v5; // r15
  __int64 **v6; // rax
  __int64 v7; // rdx
  __int64 *v8; // rdi
  __int64 v9; // rbx
  unsigned int i; // esi
  int v11; // edx
  int v12; // eax
  __int64 v13; // rcx
  int v14; // edx
  _OWORD v16[2]; // [rsp+50h] [rbp-58h] BYREF
  __int64 v17; // [rsp+70h] [rbp-38h]

  v17 = 0;
  memset(v16, 0, sizeof(v16));
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount > 0x33 )
    {
      LOWORD(v16[0]) = *(_WORD *)(WdfStructures + 408);
      goto LABEL_7;
    }
    v4 = -1;
  }
  else
  {
    v4 = 40;
  }
  LOWORD(v16[0]) = v4;
LABEL_7:
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _OWORD *))(WdfFunctions_01033 + 2128))(
    WdfDriverGlobals,
    a1,
    v16);
  v5 = *((_QWORD *)&v16[0] + 1);
  v6 = (__int64 **)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
                     WdfDriverGlobals,
                     a1,
                     off_14006BF00);
  v8 = *v6;
  v9 = **v6;
  if ( a2 < 0 )
  {
    v13 = *(_QWORD *)(v9 + 136);
    *(_QWORD *)(v9 + 144) = v8;
    XilEndpoint_FreeStreamContextArray(v13);
    ExFreePoolWithTag(*(PVOID *)(v9 + 136), 0x49434858u);
    *(_QWORD *)(v9 + 136) = 0;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v14) = 2;
      WPP_RECORDER_SF_dddd(
        *(_QWORD *)(v9 + 80),
        v14,
        13,
        121,
        (__int64)WPP_efed3b2fad403e600dcc20c948898b03_Traceguids,
        *(_BYTE *)(*(_QWORD *)(v9 + 16) + 143LL),
        *(_DWORD *)(v9 + 152),
        *((_DWORD *)v8 + 2),
        a2);
    }
    v12 = -2147481600;
  }
  else
  {
    for ( i = 1; i <= *((_DWORD *)v8 + 2); ++i )
    {
      LOBYTE(v7) = 1;
      TR_Disable_Internal(v8[13 * i - 7], v7);
    }
    XilEndpoint_FreeStreamContextArray(v8);
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01033 + 1232))(
      WdfDriverGlobals,
      *(_QWORD *)(*(_QWORD *)(v9 + 88) + 72LL));
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = 4;
      WPP_RECORDER_SF_ddd(
        *(_QWORD *)(v9 + 80),
        v11,
        13,
        120,
        (__int64)WPP_efed3b2fad403e600dcc20c948898b03_Traceguids,
        *(_BYTE *)(*(_QWORD *)(v9 + 16) + 143LL),
        *(_DWORD *)(v9 + 152),
        *((_DWORD *)v8 + 2));
    }
    v12 = 0;
  }
  *(_DWORD *)(v5 + 4) = v12;
  if ( a2 >= 0 )
    ESM_AddEsmEvent(v9, 142);
  return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01033 + 2104))(
           WdfDriverGlobals,
           a1,
           (unsigned int)a2);
}

```

## disassembly

```asm
0x1400478f0  mov     [rsp+arg_10], rbx
0x1400478f5  push    rbp
0x1400478f6  push    rsi
0x1400478f7  push    rdi
0x1400478f8  push    r14
0x1400478fa  push    r15
0x1400478fc  sub     rsp, 80h
0x140047903  mov     rax, cs:__security_cookie
0x14004790a  xor     rax, rsp
0x14004790d  mov     [rsp+0A8h+var_30], rax
0x140047912  xor     eax, eax
0x140047914  xorps   xmm0, xmm0
0x140047917  cmp     cs:WdfClientVersionHigherThanFramework, al
0x14004791d  mov     ebp, edx
0x14004791f  mov     r14, rcx
0x140047922  mov     [rsp+0A8h+var_38], rax
0x140047927  movups  [rsp+0A8h+var_58], xmm0
0x14004792c  movups  [rsp+0A8h+var_48], xmm0
0x140047931  jz      short loc_140047958
0x140047933  cmp     cs:WdfStructureCount, 33h ; '3'
0x14004793a  jbe     short loc_140047951
0x14004793c  mov     rax, cs:WdfStructures
0x140047943  movzx   ecx, word ptr [rax+198h]
0x14004794a  mov     word ptr [rsp+0A8h+var_58], cx
0x14004794f  jmp     short loc_140047962
0x140047951  mov     eax, 0FFFFh
0x140047956  jmp     short loc_14004795D
0x140047958  mov     eax, 28h ; '('
0x14004795d  mov     word ptr [rsp+0A8h+var_58], ax
0x140047962  mov     rax, cs:WdfFunctions_01033
0x140047969  lea     r8, [rsp+0A8h+var_58]
0x14004796e  mov     rcx, cs:WdfDriverGlobals
0x140047975  mov     rdx, r14
0x140047978  mov     rax, [rax+850h]
0x14004797f  call    _guard_dispatch_icall
0x140047984  mov     rax, cs:WdfFunctions_01033
0x14004798b  mov     rdx, r14
0x14004798e  mov     r8, cs:off_14006BF00
0x140047995  mov     rcx, cs:WdfDriverGlobals
0x14004799c  mov     r15, qword ptr [rsp+0A8h+var_58+8]
0x1400479a1  mov     rax, [rax+650h]
0x1400479a8  call    _guard_dispatch_icall
0x1400479ad  mov     rdi, [rax]
0x1400479b0  mov     rbx, [rdi]
0x1400479b3  test    ebp, ebp
0x1400479b5  js      loc_140047A61
0x1400479bb  mov     esi, 1
0x1400479c0  cmp     [rdi+8], esi
0x1400479c3  jb      short loc_1400479DF
0x1400479c5  lea     ecx, [rsi-1]
0x1400479c8  mov     dl, 1
0x1400479ca  imul    rcx, 68h ; 'h'
0x1400479ce  mov     rcx, [rcx+rdi+30h]
0x1400479d3  call    TR_Disable_Internal
0x1400479d8  inc     esi
0x1400479da  cmp     esi, [rdi+8]
0x1400479dd  jbe     short loc_1400479C5
0x1400479df  mov     rcx, rdi
0x1400479e2  call    XilEndpoint_FreeStreamContextArray
0x1400479e7  mov     rdx, [rbx+58h]
0x1400479eb  mov     rax, cs:WdfFunctions_01033
0x1400479f2  mov     rcx, cs:WdfDriverGlobals
0x1400479f9  mov     rdx, [rdx+48h]
0x1400479fd  mov     rax, [rax+4D0h]
0x140047a04  call    _guard_dispatch_icall
0x140047a09  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140047a10  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140047a17  jz      short loc_140047A5A
0x140047a19  mov     rax, [rbx+10h]
0x140047a1d  mov     r9d, 78h ; 'x'
0x140047a23  mov     dl, 4
0x140047a25  movzx   ecx, byte ptr [rax+8Fh]
0x140047a2c  lea     r8d, [r9-6Bh]
0x140047a30  mov     eax, [rdi+8]
0x140047a33  mov     [rsp+0A8h+var_70], eax
0x140047a37  mov     eax, [rbx+98h]
0x140047a3d  mov     [rsp+0A8h+var_78], eax
0x140047a41  lea     rax, WPP_efed3b2fad403e600dcc20c948898b03_Traceguids
0x140047a48  mov     [rsp+0A8h+var_80], ecx
0x140047a4c  mov     rcx, [rbx+50h]
0x140047a50  mov     [rsp+0A8h+var_88], rax
0x140047a55  call    WPP_RECORDER_SF_ddd
0x140047a5a  xor     eax, eax
0x140047a5c  jmp     loc_140047AF1
0x140047a61  mov     rcx, [rbx+88h]
0x140047a68  mov     [rbx+90h], rdi
0x140047a6f  call    XilEndpoint_FreeStreamContextArray
0x140047a74  mov     rcx, [rbx+88h]; P
0x140047a7b  mov     edx, 49434858h; Tag
0x140047a80  call    cs:__imp_ExFreePoolWithTag
0x140047a87  nop     dword ptr [rax+rax+00h]
0x140047a8c  mov     qword ptr [rbx+88h], 0
0x140047a97  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140047a9e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140047aa5  jz      short loc_140047AEC
0x140047aa7  mov     rax, [rbx+10h]
0x140047aab  mov     r9d, 79h ; 'y'
0x140047ab1  mov     [rsp+0A8h+var_68], ebp
0x140047ab5  mov     dl, 2
0x140047ab7  movzx   ecx, byte ptr [rax+8Fh]
0x140047abe  lea     r8d, [r9-6Ch]
0x140047ac2  mov     eax, [rdi+8]
0x140047ac5  mov     [rsp+0A8h+var_70], eax
0x140047ac9  mov     eax, [rbx+98h]
0x140047acf  mov     [rsp+0A8h+var_78], eax
0x140047ad3  lea     rax, WPP_efed3b2fad403e600dcc20c948898b03_Traceguids
0x140047ada  mov     [rsp+0A8h+var_80], ecx
0x140047ade  mov     rcx, [rbx+50h]
0x140047ae2  mov     [rsp+0A8h+var_88], rax
0x140047ae7  call    WPP_RECORDER_SF_dddd
0x140047aec  mov     eax, 80000800h
0x140047af1  mov     [r15+4], eax
0x140047af5  test    ebp, ebp
0x140047af7  js      short loc_140047B06
0x140047af9  mov     edx, 8Eh
0x140047afe  mov     rcx, rbx
0x140047b01  call    ESM_AddEsmEvent
0x140047b06  mov     rax, cs:WdfFunctions_01033
0x140047b0d  mov     r8d, ebp
0x140047b10  mov     rcx, cs:WdfDriverGlobals
0x140047b17  mov     rdx, r14
0x140047b1a  mov     rax, [rax+838h]
0x140047b21  call    _guard_dispatch_icall
0x140047b26  mov     rcx, [rsp+0A8h+var_30]
0x140047b2b  xor     rcx, rsp; StackCookie
0x140047b2e  call    __security_check_cookie
0x140047b33  mov     rbx, [rsp+0A8h+arg_10]
0x140047b3b  add     rsp, 80h
0x140047b42  pop     r15
0x140047b44  pop     r14
0x140047b46  pop     rdi
0x140047b47  pop     rsi
0x140047b48  pop     rbp
0x140047b49  retn
```
