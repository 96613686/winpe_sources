# WaasMedic::CBinaryHealthPlugin::ReportBinariesToWER(ushort * * const,ulong)

- ea: `0x180042020`
- end: `0x180042190`
- name: `?ReportBinariesToWER@CBinaryHealthPlugin@WaasMedic@@AEAAJQEAPEAGK@Z`
- size: `368`
- prototype: `int(WaasMedic::CBinaryHealthPlugin *__hidden this, unsigned __int16 **const, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, installer_update`

## callers

- `0x1800419d0`

## callees

- `0x180004708`
- `0x1800251a8`
- `0x18002543c`
- `0x18002ede4`
- `0x18002f218`
- `0x18002f608`
- `0x18002f844`
- `0x180030098`
- `0x180030464`
- `0x180042020`

## string_xrefs

- `0x180042073`: `Plugin ID is missing.`
- `0x1800420d4`: `Failed to initialize the WER reporter with default parameters and scenarios in BinaryHealthPlugin! hr=0x%08X`
- `0x18004209d`: `Failed to create instance of WER reporter in BinaryHealthPlugin! hr = 0x%08x`
- `0x180042114`: `Failed to add files to WER reporter in BinaryHealthPlugin! hr=0x%08X`
- `0x1800420f7`: `Failed to execute WER reporter in BinaryHealthPlugin! hr=0x%08X`
- `0x180042143`: `Failed to destroy instance of WER reporter in BinaryHealthPlugin! hr = 0x%08x`
- `0x18004212b`: `Failed to submit WER report in BinaryHealthPlugin! hr = 0x%08x`

## pseudocode

```c
__int64 __fastcall WaasMedic::CBinaryHealthPlugin::ReportBinariesToWER(
        const unsigned __int16 **this,
        unsigned __int16 **const a2,
        unsigned int a3)
{
  unsigned int v6; // ebx
  void *v7; // rdx
  int v8; // eax
  WaasMedic::CWERReporter *v9; // rcx
  int DefaultWERReportParamsWithScenario; // eax
  unsigned int v11; // r9d
  WaasMedic::CWERReporter *v12; // rdi
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  __int64 i; // rdi
  void *v18; // rdx
  unsigned int v20; // [rsp+30h] [rbp-69h]
  WaasMedic *v21[10]; // [rsp+40h] [rbp-59h] BYREF
  WaasMedic *v22[10]; // [rsp+90h] [rbp-9h] BYREF
  WaasMedic::CWERReporter *v23; // [rsp+100h] [rbp+67h] BYREF

  v23 = 0;
  memset_0(v21, 0, 0x48u);
  memset_0(v22, 0, 0x48u);
  if ( this[14] )
  {
    v8 = WaasMedic::CWERReporter::CreateInstance(&v23);
    v6 = v8;
    if ( v8 >= 0 )
    {
      DefaultWERReportParamsWithScenario = WaasMedic::CWERReporter::GetDefaultWERReportParamsWithScenario(
                                             v9,
                                             L"BinaryHealth",
                                             this[14],
                                             0,
                                             (unsigned __int16 **const)v21,
                                             (unsigned __int16 **const)v22,
                                             v20);
      v6 = DefaultWERReportParamsWithScenario;
      if ( DefaultWERReportParamsWithScenario >= 0 )
      {
        v12 = v23;
        v13 = WaasMedic::CWERReporter::PopulateWERReportParameters(
                v23,
                (unsigned __int16 **const)v21,
                (unsigned __int16 **const)v22,
                v11);
        v6 = v13;
        if ( v13 >= 0 )
        {
          v14 = WaasMedic::CWERReporter::AddFilesToWERReport(v12, a2, a3);
          v6 = v14;
          if ( v14 >= 0 )
          {
            v15 = WaasMedic::CWERReporter::SubmitWERReport(v12);
            v6 = v15;
            if ( v15 >= 0 )
            {
              v16 = WaasMedic::CWERReporter::DestroyInstance(&v23);
              v6 = v16;
              if ( v16 < 0 )
                LogLevelW(
                  2u,
                  L"Failed to destroy instance of WER reporter in BinaryHealthPlugin! hr = 0x%08x",
                  (unsigned int)v16);
            }
            else
            {
              LogLevelW(2u, L"Failed to submit WER report in BinaryHealthPlugin! hr = 0x%08x", (unsigned int)v15);
            }
          }
          else
          {
            LogLevelW(2u, L"Failed to add files to WER reporter in BinaryHealthPlugin! hr=0x%08X", (unsigned int)v14);
          }
        }
        else
        {
          LogLevelW(2u, L"Failed to execute WER reporter in BinaryHealthPlugin! hr=0x%08X", (unsigned int)v13);
        }
      }
      else
      {
        LogLevelW(
          2u,
          L"Failed to initialize the WER reporter with default parameters and scenarios in BinaryHealthPlugin! hr=0x%08X",
          (unsigned int)DefaultWERReportParamsWithScenario);
      }
    }
    else
    {
      LogLevelW(2u, L"Failed to create instance of WER reporter in BinaryHealthPlugin! hr = 0x%08x", (unsigned int)v8);
    }
  }
  else
  {
    v6 = -2147467261;
    LogLevelW(2u, L"Plugin ID is missing.");
  }
  for ( i = 0; i != 9; ++i )
  {
    WaasMedic::SafeFree(v21[i], v7);
    WaasMedic::SafeFree(v22[i], v18);
  }
  return v6;
}

```

## disassembly

```asm
0x180042020  mov     [rsp-8+arg_8], rbx
0x180042025  mov     [rsp-8+arg_10], rsi
0x18004202a  push    rbp
0x18004202b  push    rdi
0x18004202c  push    r14
0x18004202e  lea     rbp, [rsp-47h]
0x180042033  sub     rsp, 0E0h
0x18004203a  mov     esi, r8d
0x18004203d  mov     [rbp+57h+arg_0], 0
0x180042045  mov     r14, rdx
0x180042048  mov     rdi, rcx
0x18004204b  mov     ebx, 48h ; 'H'
0x180042050  lea     rcx, [rbp+57h+var_B0]; void *
0x180042054  mov     r8d, ebx; Size
0x180042057  xor     edx, edx; Val
0x180042059  call    memset_0
0x18004205e  mov     r8d, ebx; Size
0x180042061  lea     rcx, [rbp+57h+var_60]; void *
0x180042065  xor     edx, edx; Val
0x180042067  call    memset_0
0x18004206c  cmp     qword ptr [rdi+70h], 0
0x180042071  jnz     short loc_18004208E
0x180042073  lea     rdx, aPluginIdIsMiss; "Plugin ID is missing."
0x18004207a  mov     ecx, 2; unsigned __int8
0x18004207f  mov     ebx, 80004003h
0x180042084  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180042089  jmp     loc_180042157
0x18004208e  lea     rcx, [rbp+57h+arg_0]; struct WaasMedic::CWERReporter **
0x180042092  call    ?CreateInstance@CWERReporter@WaasMedic@@SAJPEAPEAV12@@Z; WaasMedic::CWERReporter::CreateInstance(WaasMedic::CWERReporter * *)
0x180042097  mov     ebx, eax
0x180042099  test    eax, eax
0x18004209b  jns     short loc_1800420A9
0x18004209d  lea     rdx, aFailedToCreate_7; "Failed to create instance of WER report"...
0x1800420a4  jmp     loc_18004214A
0x1800420a9  mov     r8, [rdi+70h]; unsigned __int16 *
0x1800420ad  lea     rax, [rbp+57h+var_60]
0x1800420b1  mov     [rsp+0F0h+var_C8], rax; unsigned __int16 **
0x1800420b6  lea     rdx, aBinaryhealth; "BinaryHealth"
0x1800420bd  lea     rax, [rbp+57h+var_B0]
0x1800420c1  xor     r9d, r9d; int
0x1800420c4  mov     [rsp+0F0h+var_D0], rax; unsigned __int16 **
0x1800420c9  call    ?GetDefaultWERReportParamsWithScenario@CWERReporter@WaasMedic@@QEAAJPEBG0JQEAPEAG1K@Z; WaasMedic::CWERReporter::GetDefaultWERReportParamsWithScenario(ushort const *,ushort const *,long,ushort * * const,ushort * * const,ulong)
0x1800420ce  mov     ebx, eax
0x1800420d0  test    eax, eax
0x1800420d2  jns     short loc_1800420DD
0x1800420d4  lea     rdx, aFailedToInitia_2; "Failed to initialize the WER reporter w"...
0x1800420db  jmp     short loc_18004214A
0x1800420dd  mov     rdi, [rbp+57h+arg_0]
0x1800420e1  lea     r8, [rbp+57h+var_60]; unsigned __int16 **
0x1800420e5  mov     rcx, rdi; this
0x1800420e8  lea     rdx, [rbp+57h+var_B0]; unsigned __int16 **
0x1800420ec  call    ?PopulateWERReportParameters@CWERReporter@WaasMedic@@QEAAJQEAPEAG0K@Z; WaasMedic::CWERReporter::PopulateWERReportParameters(ushort * * const,ushort * * const,ulong)
0x1800420f1  mov     ebx, eax
0x1800420f3  test    eax, eax
0x1800420f5  jns     short loc_180042100
0x1800420f7  lea     rdx, aFailedToExecut; "Failed to execute WER reporter in Binar"...
0x1800420fe  jmp     short loc_18004214A
0x180042100  mov     r8d, esi; unsigned int
0x180042103  mov     rdx, r14; unsigned __int16 **
0x180042106  mov     rcx, rdi; this
0x180042109  call    ?AddFilesToWERReport@CWERReporter@WaasMedic@@QEAAJQEAPEAGK@Z; WaasMedic::CWERReporter::AddFilesToWERReport(ushort * * const,ulong)
0x18004210e  mov     ebx, eax
0x180042110  test    eax, eax
0x180042112  jns     short loc_18004211D
0x180042114  lea     rdx, aFailedToAddFil_0; "Failed to add files to WER reporter in "...
0x18004211b  jmp     short loc_18004214A
0x18004211d  mov     rcx, rdi; this
0x180042120  call    ?SubmitWERReport@CWERReporter@WaasMedic@@QEAAJXZ; WaasMedic::CWERReporter::SubmitWERReport(void)
0x180042125  mov     ebx, eax
0x180042127  test    eax, eax
0x180042129  jns     short loc_180042134
0x18004212b  lea     rdx, aFailedToSubmit_0; "Failed to submit WER report in BinaryHe"...
0x180042132  jmp     short loc_18004214A
0x180042134  lea     rcx, [rbp+57h+arg_0]; struct WaasMedic::CWERReporter **
0x180042138  call    ?DestroyInstance@CWERReporter@WaasMedic@@SAJPEAPEAV12@@Z; WaasMedic::CWERReporter::DestroyInstance(WaasMedic::CWERReporter * *)
0x18004213d  mov     ebx, eax
0x18004213f  test    eax, eax
0x180042141  jns     short loc_180042157
0x180042143  lea     rdx, aFailedToDestro; "Failed to destroy instance of WER repor"...
0x18004214a  mov     r8d, eax
0x18004214d  mov     ecx, 2; unsigned __int8
0x180042152  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180042157  xor     edi, edi
0x180042159  mov     rcx, [rbp+rdi*8+57h+var_B0]; this
0x18004215e  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x180042163  mov     rcx, [rbp+rdi*8+57h+var_60]; this
0x180042168  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x18004216d  inc     rdi
0x180042170  cmp     rdi, 9
0x180042174  jnz     short loc_180042159
0x180042176  lea     r11, [rsp+0F0h+var_10]
0x18004217e  mov     eax, ebx
0x180042180  mov     rbx, [r11+28h]
0x180042184  mov     rsi, [r11+30h]
0x180042188  mov     rsp, r11
0x18004218b  pop     r14
0x18004218d  pop     rdi
0x18004218e  pop     rbp
0x18004218f  retn
```
