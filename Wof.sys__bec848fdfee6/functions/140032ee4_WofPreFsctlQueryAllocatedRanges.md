# WofPreFsctlQueryAllocatedRanges

- ea: `0x140032ee4`
- end: `0x1400331bf`
- name: `WofPreFsctlQueryAllocatedRanges`
- size: `731`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x140034740`

## callees

- `0x14000da78`
- `0x14000dc88`
- `0x140011560`
- `0x140011590`
- `0x140011640`
- `0x140023150`
- `0x140032ee4`
- `0x140034fa0`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x14003303d`
- `ntoskrnl!ProbeForRead` at `0x14003303d`
- `ntoskrnl!ProbeForWrite` at `0x140033055`
- `ntoskrnl!ProbeForWrite` at `0x140033055`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140033144`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140033175`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140033144`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140033175`
- `FLTMGR!FltGetStreamContext` at `0x140032f47`
- `FLTMGR!FltGetStreamContext` at `0x140032f47`
- `FLTMGR!FltReleaseContext` at `0x140033158`
- `FLTMGR!FltReleaseContext` at `0x140033186`
- `FLTMGR!FltReleaseContext` at `0x140033158`
- `FLTMGR!FltReleaseContext` at `0x140033186`

## pseudocode

```c
__int64 __fastcall WofPreFsctlQueryAllocatedRanges(__int64 a1, __int64 a2)
{
  int v4; // edx
  int v5; // edi
  __int64 v6; // rax
  _QWORD *v7; // r14
  SIZE_T v8; // r15
  void *v9; // rdi
  __int64 v10; // rdx
  _QWORD *v11; // rcx
  bool v13; // [rsp+30h] [rbp-68h] BYREF
  PFLT_CONTEXT Context; // [rsp+38h] [rbp-60h] BYREF
  int v15; // [rsp+40h] [rbp-58h]
  PEX_RUNDOWN_REF RunRef; // [rsp+48h] [rbp-50h] BYREF
  _QWORD v17[2]; // [rsp+50h] [rbp-48h] BYREF
  __int128 v18; // [rsp+60h] [rbp-38h] BYREF

  v17[1] = a1;
  Context = 0;
  v13 = 0;
  v17[0] = 0;
  v18 = 0;
  RunRef = 0;
  if ( FltGetStreamContext(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), &Context) < 0 )
    return 1;
  if ( (int)WofIsDataInFilesystemEx(Context, (_QWORD *)a2, &v13, &RunRef) < 0 || v13 )
  {
    if ( RunRef )
      ExReleaseRundownProtection(RunRef);
    FltReleaseContext(Context);
    return 1;
  }
  *(_QWORD *)(a1 + 32) = 0;
  v5 = ((__int64 (__fastcall *)(char *, _QWORD *, _QWORD))qword_14001A280[53 * *((unsigned int *)Context + 3)])(
         (char *)Context + 64,
         v17,
         0);
  if ( v5 >= 0 )
  {
    v6 = *(_QWORD *)(a1 + 16);
    v7 = *(_QWORD **)(v6 + 56);
    v8 = *(unsigned int *)(v6 + 24);
    v9 = *(void **)(v6 + 48);
    if ( *(_DWORD *)(v6 + 32) < 0x10u )
      goto LABEL_8;
    if ( *(_BYTE *)(a1 + 80)
      && (ProbeForRead(*(volatile void **)(v6 + 48), *(unsigned int *)(v6 + 32), 4u),
          ProbeForWrite(v7, v8, 4u),
          *(_BYTE *)(a1 + 80)) )
    {
      RtlCopyFromUser(&v18, v9, 0x10u);
    }
    else
    {
      RtlCopyVolatileMemory(&v18, v9, 0x10u);
    }
    if ( (__int64)v18 < 0
      || (v10 = *((_QWORD *)&v18 + 1), v18 < 0)
      || *((__int64 *)&v18 + 1) > 0x7FFFFFFFFFFFFFFFLL - (__int64)v18 )
    {
LABEL_8:
      v5 = -1073741811;
    }
    else if ( *((_QWORD *)&v18 + 1) && (__int64)v18 <= v17[0] )
    {
      if ( v17[0] - (_QWORD)v18 < *((__int64 *)&v18 + 1) )
        v10 = v17[0] - v18;
      *((_QWORD *)&v18 + 1) = v10;
      if ( (unsigned int)v8 >= 0x10 )
      {
        if ( *(_BYTE *)(a1 + 80) )
          RtlWriteULong64ToUser(v7, v18);
        else
          *v7 = v18;
        v11 = v7 + 1;
        if ( *(_BYTE *)(a1 + 80) )
          RtlWriteULong64ToUser(v11, *((__int64 *)&v18 + 1));
        else
          *v11 = *((_QWORD *)&v18 + 1);
        *(_QWORD *)(a1 + 32) = 16;
        v5 = 0;
        v15 = 0;
      }
      else
      {
        v5 = -1073741789;
      }
    }
    else
    {
      v5 = 0;
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v4) = 2;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v4,
      7,
      27,
      (__int64)WPP_dcfac5c580c33e55513b631fbc558444_Traceguids,
      v5);
  }
  if ( RunRef )
    ExReleaseRundownProtection(RunRef);
  *(_DWORD *)(a1 + 24) = v5;
  FltReleaseContext(Context);
  return 4;
}

```

## disassembly

```asm
0x140032ee4  mov     r11, rsp
0x140032ee7  mov     [r11+18h], rsi
0x140032eeb  mov     [r11+20h], rdi
0x140032eef  push    r12
0x140032ef1  push    r14
0x140032ef3  push    r15
0x140032ef5  sub     rsp, 80h
0x140032efc  mov     rax, cs:__security_cookie
0x140032f03  xor     rax, rsp
0x140032f06  mov     [rsp+98h+var_28], rax
0x140032f0b  mov     rdi, rdx
0x140032f0e  mov     rsi, rcx
0x140032f11  mov     [rsp+98h+var_40], rcx
0x140032f16  mov     qword ptr [r11-60h], 0
0x140032f1e  mov     [rsp+98h+var_68], 0
0x140032f23  mov     qword ptr [r11-48h], 0
0x140032f2b  xorps   xmm0, xmm0
0x140032f2e  movups  [rsp+98h+var_38], xmm0
0x140032f33  mov     qword ptr [r11-50h], 0
0x140032f3b  lea     r8, [r11-60h]; Context
0x140032f3f  mov     rdx, [rdx+20h]; FileObject
0x140032f43  mov     rcx, [rdi+18h]; Instance
0x140032f47  call    cs:__imp_FltGetStreamContext
0x140032f4e  nop     dword ptr [rax+rax+00h]
0x140032f53  test    eax, eax
0x140032f55  js      loc_140033192
0x140032f5b  lea     r9, [rsp+98h+RunRef]
0x140032f60  lea     r8, [rsp+98h+var_68]
0x140032f65  mov     rdx, rdi
0x140032f68  mov     rcx, [rsp+98h+Context]
0x140032f6d  call    WofIsDataInFilesystemEx
0x140032f72  test    eax, eax
0x140032f74  js      loc_14003316B
0x140032f7a  cmp     [rsp+98h+var_68], 0
0x140032f7f  jnz     loc_14003316B
0x140032f85  mov     qword ptr [rsi+20h], 0
0x140032f8d  mov     rcx, [rsp+98h+Context]
0x140032f92  mov     eax, [rcx+0Ch]
0x140032f95  imul    rdx, rax, 1A8h
0x140032f9c  lea     rax, qword_14001A280
0x140032fa3  add     rcx, 40h ; '@'
0x140032fa7  mov     rax, [rdx+rax]
0x140032fab  xor     r8d, r8d
0x140032fae  lea     rdx, [rsp+98h+var_48]
0x140032fb3  call    _guard_dispatch_icall
0x140032fb8  mov     edi, eax
0x140032fba  test    eax, eax
0x140032fbc  jns     short loc_140033003
0x140032fbe  lea     rax, WPP_RECORDER_INITIALIZED
0x140032fc5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140032fcc  jz      loc_14003313A
0x140032fd2  mov     r9d, 1Bh
0x140032fd8  mov     [rsp+98h+var_70], edi
0x140032fdc  lea     rax, WPP_dcfac5c580c33e55513b631fbc558444_Traceguids
0x140032fe3  mov     [rsp+98h+var_78], rax
0x140032fe8  lea     r8d, [r9-14h]
0x140032fec  mov     dl, 2
0x140032fee  mov     rcx, cs:WPP_GLOBAL_Control
0x140032ff5  mov     rcx, [rcx+40h]
0x140032ff9  call    WPP_RECORDER_SF_d
0x140032ffe  jmp     loc_14003313A
0x140033003  mov     rax, [rsi+10h]
0x140033007  mov     r14, [rax+38h]
0x14003300b  mov     r15d, [rax+18h]
0x14003300f  mov     rdi, [rax+30h]
0x140033013  mov     ecx, [rax+20h]
0x140033016  mov     r12d, 10h
0x14003301c  cmp     ecx, r12d
0x14003301f  jnb     short loc_14003302B
0x140033021  mov     edi, 0C000000Dh
0x140033026  jmp     loc_14003313A
0x14003302b  cmp     byte ptr [rsi+50h], 0
0x14003302f  jz      short loc_140033079
0x140033031  mov     rdx, rcx; Length
0x140033034  mov     r8d, 4; Alignment
0x14003303a  mov     rcx, rdi; Address
0x14003303d  call    cs:__imp_ProbeForRead
0x140033044  nop     dword ptr [rax+rax+00h]
0x140033049  mov     rdx, r15; Length
0x14003304c  mov     r8d, 4; Alignment
0x140033052  mov     rcx, r14; Address
0x140033055  call    cs:__imp_ProbeForWrite
0x14003305c  nop     dword ptr [rax+rax+00h]
0x140033061  cmp     byte ptr [rsi+50h], 0
0x140033065  jz      short loc_140033079
0x140033067  mov     r8, r12; Size
0x14003306a  mov     rdx, rdi; Src
0x14003306d  lea     rcx, [rsp+98h+var_38]; void *
0x140033072  call    RtlCopyFromUser
0x140033077  jmp     short loc_14003308A
0x140033079  mov     r8, r12; Size
0x14003307c  mov     rdx, rdi; Src
0x14003307f  lea     rcx, [rsp+98h+var_38]; void *
0x140033084  call    RtlCopyVolatileMemory
0x140033089  nop
0x14003308a  mov     rcx, qword ptr [rsp+98h+var_38]
0x14003308f  test    rcx, rcx
0x140033092  js      short loc_140033021
0x140033094  mov     rdx, qword ptr [rsp+98h+var_38+8]
0x140033099  test    rdx, rdx
0x14003309c  js      short loc_140033021
0x14003309e  mov     rax, 7FFFFFFFFFFFFFFFh
0x1400330a8  sub     rax, rcx
0x1400330ab  cmp     rdx, rax
0x1400330ae  jg      loc_140033021
0x1400330b4  test    rdx, rdx
0x1400330b7  jz      short loc_14003312C
0x1400330b9  mov     rax, [rsp+98h+var_48]
0x1400330be  cmp     rcx, rax
0x1400330c1  jg      short loc_14003312C
0x1400330c3  sub     rax, rcx
0x1400330c6  cmp     rax, rdx
0x1400330c9  cmovl   rdx, rax
0x1400330cd  mov     qword ptr [rsp+98h+var_38+8], rdx
0x1400330d2  cmp     r15d, r12d
0x1400330d5  jnb     short loc_1400330DE
0x1400330d7  mov     edi, 0C0000023h
0x1400330dc  jmp     short loc_14003313A
0x1400330de  cmp     byte ptr [rsi+50h], 0
0x1400330e2  jz      short loc_1400330F1
0x1400330e4  mov     rdx, rcx
0x1400330e7  mov     rcx, r14
0x1400330ea  call    RtlWriteULong64ToUser
0x1400330ef  jmp     short loc_1400330F4
0x1400330f1  mov     [r14], rcx
0x1400330f4  mov     rax, qword ptr [rsp+98h+var_38+8]
0x1400330f9  lea     rcx, [r14+8]
0x1400330fd  cmp     byte ptr [rsi+50h], 0
0x140033101  jz      short loc_14003310D
0x140033103  mov     rdx, rax
0x140033106  call    RtlWriteULong64ToUser
0x14003310b  jmp     short loc_140033110
0x14003310d  mov     [rcx], rax
0x140033110  mov     [rsi+20h], r12
0x140033114  xor     edi, edi
0x140033116  mov     [rsp+98h+var_58], edi
0x14003311a  jmp     short loc_14003313A
0x14003311c  mov     edi, 0C00000E8h
0x140033121  mov     [rsp+98h+var_58], edi
0x140033125  mov     rsi, [rsp+98h+var_40]
0x14003312a  jmp     short loc_14003313A
0x14003312c  xor     edi, edi
0x14003312e  jmp     short loc_14003313A
0x140033130  mov     edi, 0C00000E8h
0x140033135  mov     rsi, [rsp+98h+var_40]
0x14003313a  mov     rcx, [rsp+98h+RunRef]; RunRef
0x14003313f  test    rcx, rcx
0x140033142  jz      short loc_140033150
0x140033144  call    cs:__imp_ExReleaseRundownProtection
0x14003314b  nop     dword ptr [rax+rax+00h]
0x140033150  mov     [rsi+18h], edi
0x140033153  mov     rcx, [rsp+98h+Context]; Context
0x140033158  call    cs:__imp_FltReleaseContext
0x14003315f  nop     dword ptr [rax+rax+00h]
0x140033164  mov     eax, 4
0x140033169  jmp     short loc_140033197
0x14003316b  mov     rcx, [rsp+98h+RunRef]; RunRef
0x140033170  test    rcx, rcx
0x140033173  jz      short loc_140033181
0x140033175  call    cs:__imp_ExReleaseRundownProtection
0x14003317c  nop     dword ptr [rax+rax+00h]
0x140033181  mov     rcx, [rsp+98h+Context]; Context
0x140033186  call    cs:__imp_FltReleaseContext
0x14003318d  nop     dword ptr [rax+rax+00h]
0x140033192  mov     eax, 1
0x140033197  mov     rcx, [rsp+98h+var_28]
0x14003319c  xor     rcx, rsp; StackCookie
0x14003319f  call    __security_check_cookie
0x1400331a4  lea     r11, [rsp+98h+var_18]
0x1400331ac  mov     rsi, [r11+30h]
0x1400331b0  mov     rdi, [r11+38h]
0x1400331b4  mov     rsp, r11
0x1400331b7  pop     r15
0x1400331b9  pop     r14
0x1400331bb  pop     r12
0x1400331bd  retn
```
