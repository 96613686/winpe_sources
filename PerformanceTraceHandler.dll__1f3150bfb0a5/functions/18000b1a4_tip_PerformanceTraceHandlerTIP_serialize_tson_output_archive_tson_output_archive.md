# _tip_PerformanceTraceHandlerTIP::serialize<tson::output_archive>(tson::output_archive &)

- ea: `0x18000b1a4`
- end: `0x18000b395`
- name: `??$serialize@Voutput_archive@tson@@@_tip_PerformanceTraceHandlerTIP@@QEAAXAEAVoutput_archive@tson@@@Z`
- size: `497`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e3f0`

## callees

- `0x18000a664`
- `0x18000ada4`

## string_xrefs

- `0x18000b1ec`: `showedCompletionToast`
- `0x18000b1ff`: `gotFileToken`
- `0x18000b212`: `gotZipPath`
- `0x18000b225`: `movedToOutputFolder`
- `0x18000b24b`: `gotOutputPath`
- `0x18000b271`: `gotTempPath`
- `0x18000b2ad`: `gotTracesPath`

## pseudocode

```c
__int64 __fastcall _tip_PerformanceTraceHandlerTIP::serialize<tson::output_archive>(__int64 a1, __int64 a2)
{
  int v2; // ebx
  const char *v4; // [rsp+70h] [rbp-90h] BYREF
  char v5; // [rsp+78h] [rbp-88h]
  __int64 v6; // [rsp+80h] [rbp-80h]
  const char *v7; // [rsp+88h] [rbp-78h] BYREF
  char v8; // [rsp+90h] [rbp-70h]
  __int64 v9; // [rsp+98h] [rbp-68h]
  const char *v10; // [rsp+A0h] [rbp-60h] BYREF
  char v11; // [rsp+A8h] [rbp-58h]
  __int64 v12; // [rsp+B0h] [rbp-50h]
  const char *v13; // [rsp+B8h] [rbp-48h] BYREF
  char v14; // [rsp+C0h] [rbp-40h]
  __int64 v15; // [rsp+C8h] [rbp-38h]
  const char *v16; // [rsp+D0h] [rbp-30h] BYREF
  char v17; // [rsp+D8h] [rbp-28h]
  __int64 v18; // [rsp+E0h] [rbp-20h]
  const char *v19; // [rsp+E8h] [rbp-18h] BYREF
  char v20; // [rsp+F0h] [rbp-10h]
  __int64 v21; // [rsp+F8h] [rbp-8h]
  const char *v22; // [rsp+100h] [rbp+0h] BYREF
  char v23; // [rsp+108h] [rbp+8h]
  __int64 v24; // [rsp+110h] [rbp+10h]
  const char *v25; // [rsp+118h] [rbp+18h] BYREF
  char v26; // [rsp+120h] [rbp+20h]
  __int64 v27; // [rsp+128h] [rbp+28h]
  const char *v28; // [rsp+130h] [rbp+30h] BYREF
  char v29; // [rsp+138h] [rbp+38h]
  __int64 v30; // [rsp+140h] [rbp+40h]
  const char *v31; // [rsp+148h] [rbp+48h] BYREF
  char v32; // [rsp+150h] [rbp+50h]
  __int64 v33; // [rsp+158h] [rbp+58h]
  const char *v34; // [rsp+160h] [rbp+60h] BYREF
  char v35; // [rsp+168h] [rbp+68h]
  __int64 v36; // [rsp+170h] [rbp+70h]
  const char *v37; // [rsp+178h] [rbp+78h] BYREF
  char v38; // [rsp+180h] [rbp+80h]
  __int64 v39; // [rsp+188h] [rbp+88h]
  const char *v40; // [rsp+190h] [rbp+90h] BYREF
  char v41; // [rsp+198h] [rbp+98h]
  __int64 v42; // [rsp+1A0h] [rbp+A0h]

  *(_BYTE *)(a2 + 8) = 16;
  v4 = "showedErrorToast";
  v2 = a2;
  v5 = 16;
  v6 = a1 + 29;
  v7 = "showedStartingToast";
  v9 = a1 + 28;
  v10 = "showedCompletionToast";
  v12 = a1 + 27;
  v13 = "gotFileToken";
  v15 = a1 + 26;
  v16 = "gotZipPath";
  v18 = a1 + 25;
  v19 = "movedToOutputFolder";
  v21 = a1 + 24;
  v22 = "ensuredOutputFolder";
  v24 = a1 + 23;
  v25 = "gotOutputPath";
  v27 = a1 + 22;
  v28 = "stoppedTrace";
  v30 = a1 + 21;
  v31 = "gotTempPath";
  v33 = a1 + 20;
  v34 = "ensuredTracesFolder";
  v36 = a1 + 19;
  v37 = "startedTrace";
  v39 = a1 + 18;
  v40 = "gotTracesPath";
  v42 = a1 + 17;
  *(_QWORD *)a2 = "scenarioIsActive";
  v8 = 19;
  v11 = 21;
  v14 = 12;
  v17 = 10;
  v20 = 19;
  v23 = 19;
  v26 = 13;
  v29 = 12;
  v32 = 11;
  v35 = 19;
  v38 = 12;
  v41 = 13;
  tson::output_archive::operator()<bool &>(a2, a1 + 16);
  return tson::output_archive::process<tson::nvp<bool &>,tson::nvp<bool &>,tson::nvp<bool &>,tson::nvp<bool &>,tson::nvp<bool &>,tson::nvp<bool &>,tson::nvp<bool &>,tson::nvp<bool &>,tson::nvp<bool &>,tson::nvp<bool &>,tson::nvp<bool &>,tson::nvp<bool &>,tson::nvp<bool &>>(
           v2,
           (unsigned int)&v40,
           (unsigned int)&v37,
           (unsigned int)&v34,
           (__int64)&v31,
           (__int64)&v28,
           (__int64)&v25,
           (__int64)&v22,
           (__int64)&v19,
           (__int64)&v16,
           (__int64)&v13,
           (__int64)&v10,
           (__int64)&v7,
           (__int64)&v4);
}

```

## disassembly

```asm
0x18000b1a4  mov     [rsp-8+arg_0], rbx
0x18000b1a9  push    rbp
0x18000b1aa  lea     rbp, [rsp-0B0h]
0x18000b1b2  sub     rsp, 1B0h
0x18000b1b9  lea     rax, aShowederrortoa; "showedErrorToast"
0x18000b1c0  mov     byte ptr [rdx+8], 10h
0x18000b1c4  mov     [rsp+1B0h+var_140], rax
0x18000b1c9  mov     rbx, rdx
0x18000b1cc  lea     rax, [rcx+1Dh]
0x18000b1d0  mov     [rsp+1B0h+var_138], 10h
0x18000b1d5  mov     [rbp+0B0h+var_130], rax
0x18000b1d9  lea     rax, aShowedstarting; "showedStartingToast"
0x18000b1e0  mov     [rbp+0B0h+var_128], rax
0x18000b1e4  lea     rax, [rcx+1Ch]
0x18000b1e8  mov     [rbp+0B0h+var_118], rax
0x18000b1ec  lea     rax, aShowedcompleti; "showedCompletionToast"
0x18000b1f3  mov     [rbp+0B0h+var_110], rax
0x18000b1f7  lea     rax, [rcx+1Bh]
0x18000b1fb  mov     [rbp+0B0h+var_100], rax
0x18000b1ff  lea     rax, aGotfiletoken; "gotFileToken"
0x18000b206  mov     [rbp+0B0h+var_F8], rax
0x18000b20a  lea     rax, [rcx+1Ah]
0x18000b20e  mov     [rbp+0B0h+var_E8], rax
0x18000b212  lea     rax, aGotzippath; "gotZipPath"
0x18000b219  mov     [rbp+0B0h+var_E0], rax
0x18000b21d  lea     rax, [rcx+19h]
0x18000b221  mov     [rbp+0B0h+var_D0], rax
0x18000b225  lea     rax, aMovedtooutputf; "movedToOutputFolder"
0x18000b22c  mov     [rbp+0B0h+var_C8], rax
0x18000b230  lea     rax, [rcx+18h]
0x18000b234  mov     [rbp+0B0h+var_B8], rax
0x18000b238  lea     rax, aEnsuredoutputf; "ensuredOutputFolder"
0x18000b23f  mov     [rbp+0B0h+var_B0], rax
0x18000b243  lea     rax, [rcx+17h]
0x18000b247  mov     [rbp+0B0h+var_A0], rax
0x18000b24b  lea     rax, aGotoutputpath; "gotOutputPath"
0x18000b252  mov     [rbp+0B0h+var_98], rax
0x18000b256  lea     rax, [rcx+16h]
0x18000b25a  mov     [rbp+0B0h+var_88], rax
0x18000b25e  lea     rax, aStoppedtrace; "stoppedTrace"
0x18000b265  mov     [rbp+0B0h+var_80], rax
0x18000b269  lea     rax, [rcx+15h]
0x18000b26d  mov     [rbp+0B0h+var_70], rax
0x18000b271  lea     rax, aGottemppath; "gotTempPath"
0x18000b278  mov     [rbp+0B0h+var_68], rax
0x18000b27c  lea     rax, [rcx+14h]
0x18000b280  mov     [rbp+0B0h+var_58], rax
0x18000b284  lea     rax, aEnsuredtracesf; "ensuredTracesFolder"
0x18000b28b  mov     [rbp+0B0h+var_50], rax
0x18000b28f  lea     rax, [rcx+13h]
0x18000b293  mov     [rbp+0B0h+var_40], rax
0x18000b297  lea     rax, aStartedtrace; "startedTrace"
0x18000b29e  mov     [rbp+0B0h+var_38], rax
0x18000b2a2  lea     rax, [rcx+12h]
0x18000b2a6  mov     [rbp+0B0h+var_28], rax
0x18000b2ad  lea     rax, aGottracespath; "gotTracesPath"
0x18000b2b4  mov     [rbp+0B0h+var_20], rax
0x18000b2bb  lea     rax, [rcx+11h]
0x18000b2bf  mov     [rbp+0B0h+var_10], rax
0x18000b2c6  lea     rax, aScenarioisacti; "scenarioIsActive"
0x18000b2cd  mov     [rdx], rax
0x18000b2d0  lea     rdx, [rcx+10h]
0x18000b2d4  mov     rcx, rbx
0x18000b2d7  mov     [rbp+0B0h+var_120], 13h
0x18000b2db  mov     [rbp+0B0h+var_108], 15h
0x18000b2df  mov     [rbp+0B0h+var_F0], 0Ch
0x18000b2e3  mov     [rbp+0B0h+var_D8], 0Ah
0x18000b2e7  mov     [rbp+0B0h+var_C0], 13h
0x18000b2eb  mov     [rbp+0B0h+var_A8], 13h
0x18000b2ef  mov     [rbp+0B0h+var_90], 0Dh
0x18000b2f3  mov     [rbp+0B0h+var_78], 0Ch
0x18000b2f7  mov     [rbp+0B0h+var_60], 0Bh
0x18000b2fb  mov     [rbp+0B0h+var_48], 13h
0x18000b2ff  mov     [rbp+0B0h+var_30], 0Ch
0x18000b306  mov     [rbp+0B0h+var_18], 0Dh
0x18000b30d  call    ??$?RAEA_N@output_archive@tson@@QEAAAEAV01@AEA_N@Z; tson::output_archive::operator()<bool &>(bool &)
0x18000b312  lea     rax, [rsp+1B0h+var_140]
0x18000b317  mov     [rsp+1B0h+var_148], rax
0x18000b31c  lea     rax, [rbp+0B0h+var_128]
0x18000b320  mov     [rsp+1B0h+var_150], rax
0x18000b325  lea     rax, [rbp+0B0h+var_110]
0x18000b329  mov     [rsp+1B0h+var_158], rax
0x18000b32e  lea     rax, [rbp+0B0h+var_F8]
0x18000b332  mov     [rsp+1B0h+var_160], rax
0x18000b337  lea     rax, [rbp+0B0h+var_E0]
0x18000b33b  mov     [rsp+1B0h+var_168], rax
0x18000b340  lea     r9, [rbp+0B0h+var_50]
0x18000b344  lea     rax, [rbp+0B0h+var_C8]
0x18000b348  mov     rcx, rbx
0x18000b34b  mov     [rsp+1B0h+var_170], rax
0x18000b350  lea     r8, [rbp+0B0h+var_38]
0x18000b354  lea     rax, [rbp+0B0h+var_B0]
0x18000b358  mov     [rsp+1B0h+var_178], rax
0x18000b35d  lea     rdx, [rbp+0B0h+var_20]
0x18000b364  lea     rax, [rbp+0B0h+var_98]
0x18000b368  mov     [rsp+1B0h+var_180], rax
0x18000b36d  lea     rax, [rbp+0B0h+var_80]
0x18000b371  mov     [rsp+1B0h+var_188], rax
0x18000b376  lea     rax, [rbp+0B0h+var_68]
0x18000b37a  mov     [rsp+1B0h+var_190], rax
0x18000b37f  call    ??$process@V?$nvp@AEA_N@tson@@V12@V12@V12@V12@V12@V12@V12@V12@V12@V12@V12@V12@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@000000000000@Z; tson::output_archive::process<tson::nvp<bool &>,tson::nvp<bool &>,tson::nvp<bool &>,tson::nvp<bool &>,tson::nvp<bool &>,tson::nvp<bool &>,tson::nvp<bool &>,tson::nvp<bool &>,tson::nvp<bool &>,tson::nvp<bool &>,tson::nvp<bool &>,tson::nvp<bool &>,tson::nvp<bool &>>(tson::nvp<bool &> &&,tson::nvp<bool &> &&,tson::nvp<bool &> &&,tson::nvp<bool &> &&,tson::nvp<bool &> &&,tson::nvp<bool &> &&,tson::nvp<bool &> &&,tson::nvp<bool &> &&,tson::nvp<bool &> &&,tson::nvp<bool &> &&,tson::nvp<bool &> &&,tson::nvp<bool &> &&,tson::nvp<bool &> &&)
0x18000b384  mov     rbx, [rsp+1B0h+arg_0]
0x18000b38c  add     rsp, 1B0h
0x18000b393  pop     rbp
0x18000b394  retn
```
