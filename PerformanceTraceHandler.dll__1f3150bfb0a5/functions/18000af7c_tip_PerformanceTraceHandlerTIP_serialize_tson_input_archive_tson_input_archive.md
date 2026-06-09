# _tip_PerformanceTraceHandlerTIP::serialize<tson::input_archive>(tson::input_archive &)

- ea: `0x18000af7c`
- end: `0x18000b19c`
- name: `??$serialize@Vinput_archive@tson@@@_tip_PerformanceTraceHandlerTIP@@QEAAXAEAVinput_archive@tson@@@Z`
- size: `544`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a860`

## callees

- `0x18000ab9c`

## string_xrefs

- `0x18000afc8`: `showedCompletionToast`
- `0x18000afdb`: `gotFileToken`
- `0x18000afee`: `gotZipPath`
- `0x18000b001`: `movedToOutputFolder`
- `0x18000b027`: `gotOutputPath`
- `0x18000b04d`: `gotTempPath`
- `0x18000b08a`: `gotTracesPath`

## pseudocode

```c
__int64 __fastcall _tip_PerformanceTraceHandlerTIP::serialize<tson::input_archive>(__int64 a1, __int64 a2)
{
  const char *v4; // [rsp+20h] [rbp-E0h] BYREF
  char v5; // [rsp+28h] [rbp-D8h]
  __int64 v6; // [rsp+30h] [rbp-D0h]
  const char *v7; // [rsp+38h] [rbp-C8h] BYREF
  char v8; // [rsp+40h] [rbp-C0h]
  __int64 v9; // [rsp+48h] [rbp-B8h]
  const char *v10; // [rsp+50h] [rbp-B0h] BYREF
  char v11; // [rsp+58h] [rbp-A8h]
  __int64 v12; // [rsp+60h] [rbp-A0h]
  const char *v13; // [rsp+68h] [rbp-98h] BYREF
  char v14; // [rsp+70h] [rbp-90h]
  __int64 v15; // [rsp+78h] [rbp-88h]
  const char *v16; // [rsp+80h] [rbp-80h] BYREF
  char v17; // [rsp+88h] [rbp-78h]
  __int64 v18; // [rsp+90h] [rbp-70h]
  const char *v19; // [rsp+98h] [rbp-68h] BYREF
  char v20; // [rsp+A0h] [rbp-60h]
  __int64 v21; // [rsp+A8h] [rbp-58h]
  const char *v22; // [rsp+B0h] [rbp-50h] BYREF
  char v23; // [rsp+B8h] [rbp-48h]
  __int64 v24; // [rsp+C0h] [rbp-40h]
  const char *v25; // [rsp+C8h] [rbp-38h] BYREF
  char v26; // [rsp+D0h] [rbp-30h]
  __int64 v27; // [rsp+D8h] [rbp-28h]
  const char *v28; // [rsp+E0h] [rbp-20h] BYREF
  char v29; // [rsp+E8h] [rbp-18h]
  __int64 v30; // [rsp+F0h] [rbp-10h]
  const char *v31; // [rsp+F8h] [rbp-8h] BYREF
  char v32; // [rsp+100h] [rbp+0h]
  __int64 v33; // [rsp+108h] [rbp+8h]
  const char *v34; // [rsp+110h] [rbp+10h] BYREF
  char v35; // [rsp+118h] [rbp+18h]
  __int64 v36; // [rsp+120h] [rbp+20h]
  const char *v37; // [rsp+128h] [rbp+28h] BYREF
  char v38; // [rsp+130h] [rbp+30h]
  __int64 v39; // [rsp+138h] [rbp+38h]
  const char *v40; // [rsp+140h] [rbp+40h] BYREF
  char v41; // [rsp+148h] [rbp+48h]
  __int64 v42; // [rsp+150h] [rbp+50h]
  const char *v43; // [rsp+158h] [rbp+58h] BYREF
  char v44; // [rsp+160h] [rbp+60h]
  __int64 v45; // [rsp+168h] [rbp+68h]

  v44 = 16;
  v43 = "showedErrorToast";
  v41 = 19;
  v45 = a1 + 29;
  v38 = 21;
  v40 = "showedStartingToast";
  v42 = a1 + 28;
  v37 = "showedCompletionToast";
  v39 = a1 + 27;
  v34 = "gotFileToken";
  v36 = a1 + 26;
  v31 = "gotZipPath";
  v33 = a1 + 25;
  v28 = "movedToOutputFolder";
  v30 = a1 + 24;
  v25 = "ensuredOutputFolder";
  v27 = a1 + 23;
  v22 = "gotOutputPath";
  v24 = a1 + 22;
  v19 = "stoppedTrace";
  v21 = a1 + 21;
  v16 = "gotTempPath";
  v18 = a1 + 20;
  v13 = "ensuredTracesFolder";
  v15 = a1 + 19;
  v10 = "startedTrace";
  v12 = a1 + 18;
  v7 = "gotTracesPath";
  v9 = a1 + 17;
  v4 = "scenarioIsActive";
  v6 = a1 + 16;
  v35 = 12;
  v32 = 10;
  v29 = 19;
  v26 = 19;
  v23 = 13;
  v20 = 12;
  v17 = 11;
  v14 = 19;
  v11 = 12;
  v8 = 13;
  v5 = 16;
  tson::input_archive::process<tson::nvp<bool &>>(a2, &v4);
  tson::input_archive::process<tson::nvp<bool &>>(a2, &v7);
  tson::input_archive::process<tson::nvp<bool &>>(a2, &v10);
  tson::input_archive::process<tson::nvp<bool &>>(a2, &v13);
  tson::input_archive::process<tson::nvp<bool &>>(a2, &v16);
  tson::input_archive::process<tson::nvp<bool &>>(a2, &v19);
  tson::input_archive::process<tson::nvp<bool &>>(a2, &v22);
  tson::input_archive::process<tson::nvp<bool &>>(a2, &v25);
  tson::input_archive::process<tson::nvp<bool &>>(a2, &v28);
  tson::input_archive::process<tson::nvp<bool &>>(a2, &v31);
  tson::input_archive::process<tson::nvp<bool &>>(a2, &v34);
  tson::input_archive::process<tson::nvp<bool &>>(a2, &v37);
  tson::input_archive::process<tson::nvp<bool &>>(a2, &v40);
  return tson::input_archive::process<tson::nvp<bool &>>(a2, &v43);
}

```

## disassembly

```asm
0x18000af7c  mov     [rsp-8+arg_0], rbx
0x18000af81  push    rbp
0x18000af82  lea     rbp, [rsp-70h]
0x18000af87  sub     rsp, 170h
0x18000af8e  lea     rax, aShowederrortoa; "showedErrorToast"
0x18000af95  mov     [rbp+70h+var_10], 10h
0x18000af99  mov     [rbp+70h+var_18], rax
0x18000af9d  mov     rbx, rdx
0x18000afa0  lea     rax, [rcx+1Dh]
0x18000afa4  mov     [rbp+70h+var_28], 13h
0x18000afa8  mov     [rbp+70h+var_8], rax
0x18000afac  lea     rdx, [rsp+170h+var_150]
0x18000afb1  lea     rax, aShowedstarting; "showedStartingToast"
0x18000afb8  mov     [rbp+70h+var_40], 15h
0x18000afbc  mov     [rbp+70h+var_30], rax
0x18000afc0  lea     rax, [rcx+1Ch]
0x18000afc4  mov     [rbp+70h+var_20], rax
0x18000afc8  lea     rax, aShowedcompleti; "showedCompletionToast"
0x18000afcf  mov     [rbp+70h+var_48], rax
0x18000afd3  lea     rax, [rcx+1Bh]
0x18000afd7  mov     [rbp+70h+var_38], rax
0x18000afdb  lea     rax, aGotfiletoken; "gotFileToken"
0x18000afe2  mov     [rbp+70h+var_60], rax
0x18000afe6  lea     rax, [rcx+1Ah]
0x18000afea  mov     [rbp+70h+var_50], rax
0x18000afee  lea     rax, aGotzippath; "gotZipPath"
0x18000aff5  mov     [rbp+70h+var_78], rax
0x18000aff9  lea     rax, [rcx+19h]
0x18000affd  mov     [rbp+70h+var_68], rax
0x18000b001  lea     rax, aMovedtooutputf; "movedToOutputFolder"
0x18000b008  mov     [rbp+70h+var_90], rax
0x18000b00c  lea     rax, [rcx+18h]
0x18000b010  mov     [rbp+70h+var_80], rax
0x18000b014  lea     rax, aEnsuredoutputf; "ensuredOutputFolder"
0x18000b01b  mov     [rbp+70h+var_A8], rax
0x18000b01f  lea     rax, [rcx+17h]
0x18000b023  mov     [rbp+70h+var_98], rax
0x18000b027  lea     rax, aGotoutputpath; "gotOutputPath"
0x18000b02e  mov     [rbp+70h+var_C0], rax
0x18000b032  lea     rax, [rcx+16h]
0x18000b036  mov     [rbp+70h+var_B0], rax
0x18000b03a  lea     rax, aStoppedtrace; "stoppedTrace"
0x18000b041  mov     [rbp+70h+var_D8], rax
0x18000b045  lea     rax, [rcx+15h]
0x18000b049  mov     [rbp+70h+var_C8], rax
0x18000b04d  lea     rax, aGottemppath; "gotTempPath"
0x18000b054  mov     [rbp+70h+var_F0], rax
0x18000b058  lea     rax, [rcx+14h]
0x18000b05c  mov     [rbp+70h+var_E0], rax
0x18000b060  lea     rax, aEnsuredtracesf; "ensuredTracesFolder"
0x18000b067  mov     [rsp+170h+var_108], rax
0x18000b06c  lea     rax, [rcx+13h]
0x18000b070  mov     [rsp+170h+var_F8], rax
0x18000b075  lea     rax, aStartedtrace; "startedTrace"
0x18000b07c  mov     [rsp+170h+var_120], rax
0x18000b081  lea     rax, [rcx+12h]
0x18000b085  mov     [rsp+170h+var_110], rax
0x18000b08a  lea     rax, aGottracespath; "gotTracesPath"
0x18000b091  mov     [rsp+170h+var_138], rax
0x18000b096  lea     rax, [rcx+11h]
0x18000b09a  mov     [rsp+170h+var_128], rax
0x18000b09f  lea     rax, aScenarioisacti; "scenarioIsActive"
0x18000b0a6  mov     [rsp+170h+var_150], rax
0x18000b0ab  lea     rax, [rcx+10h]
0x18000b0af  mov     rcx, rbx
0x18000b0b2  mov     [rsp+170h+var_140], rax
0x18000b0b7  mov     [rbp+70h+var_58], 0Ch
0x18000b0bb  mov     [rbp+70h+var_70], 0Ah
0x18000b0bf  mov     [rbp+70h+var_88], 13h
0x18000b0c3  mov     [rbp+70h+var_A0], 13h
0x18000b0c7  mov     [rbp+70h+var_B8], 0Dh
0x18000b0cb  mov     [rbp+70h+var_D0], 0Ch
0x18000b0cf  mov     [rbp+70h+var_E8], 0Bh
0x18000b0d3  mov     [rsp+170h+var_100], 13h
0x18000b0d8  mov     [rsp+170h+var_118], 0Ch
0x18000b0dd  mov     [rsp+170h+var_130], 0Dh
0x18000b0e2  mov     [rsp+170h+var_148], 10h
0x18000b0e7  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x18000b0ec  lea     rdx, [rsp+170h+var_138]
0x18000b0f1  mov     rcx, rbx
0x18000b0f4  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x18000b0f9  lea     rdx, [rsp+170h+var_120]
0x18000b0fe  mov     rcx, rbx
0x18000b101  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x18000b106  lea     rdx, [rsp+170h+var_108]
0x18000b10b  mov     rcx, rbx
0x18000b10e  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x18000b113  lea     rdx, [rbp+70h+var_F0]
0x18000b117  mov     rcx, rbx
0x18000b11a  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x18000b11f  lea     rdx, [rbp+70h+var_D8]
0x18000b123  mov     rcx, rbx
0x18000b126  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x18000b12b  lea     rdx, [rbp+70h+var_C0]
0x18000b12f  mov     rcx, rbx
0x18000b132  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x18000b137  lea     rdx, [rbp+70h+var_A8]
0x18000b13b  mov     rcx, rbx
0x18000b13e  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x18000b143  lea     rdx, [rbp+70h+var_90]
0x18000b147  mov     rcx, rbx
0x18000b14a  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x18000b14f  lea     rdx, [rbp+70h+var_78]
0x18000b153  mov     rcx, rbx
0x18000b156  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x18000b15b  lea     rdx, [rbp+70h+var_60]
0x18000b15f  mov     rcx, rbx
0x18000b162  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x18000b167  lea     rdx, [rbp+70h+var_48]
0x18000b16b  mov     rcx, rbx
0x18000b16e  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x18000b173  lea     rdx, [rbp+70h+var_30]
0x18000b177  mov     rcx, rbx
0x18000b17a  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x18000b17f  lea     rdx, [rbp+70h+var_18]
0x18000b183  mov     rcx, rbx
0x18000b186  call    ??$process@V?$nvp@AEA_N@tson@@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEA_N@1@@Z; tson::input_archive::process<tson::nvp<bool &>>(tson::nvp<bool &> &&)
0x18000b18b  mov     rbx, [rsp+170h+arg_0]
0x18000b193  add     rsp, 170h
0x18000b19a  pop     rbp
0x18000b19b  retn
```
