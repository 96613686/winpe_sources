# BasepCreateProcessParameters

- ea: `0x1800e7570`
- end: `0x1800e7aa2`
- name: `BasepCreateProcessParameters`
- size: `1330`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18007f610`

## callees

- `0x1800134a0`
- `0x1800e7570`
- `0x18012d119`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800e786b`
- `ntdll!RtlInitUnicodeString` at `0x1800e786b`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800e7603`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800e761b`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800e763a`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800e7651`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800e767f`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800e7697`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800e76ce`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800e7603`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800e761b`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800e763a`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800e7651`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800e767f`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800e7697`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800e76ce`
- `ntdll!RtlFreeHeap` at `0x1800e7a15`
- `ntdll!RtlFreeHeap` at `0x1800e7a15`
- `ntdll!RtlDestroyProcessParameters` at `0x1800e7a97`
- `ntdll!RtlDestroyProcessParameters` at `0x1800e7a97`
- `ntdll!LdrGetDllDirectory` at `0x1800e7855`
- `ntdll!LdrGetDllDirectory` at `0x1800e79d9`
- `ntdll!LdrGetDllDirectory` at `0x1800e7855`
- `ntdll!LdrGetDllDirectory` at `0x1800e79d9`
- `ntdll!RtlCreateProcessParametersWithTemplate` at `0x1800e76ee`
- `ntdll!RtlCreateProcessParametersWithTemplate` at `0x1800e76ee`
- `ntdll!RtlAllocateHeap` at `0x1800e79be`
- `ntdll!RtlAllocateHeap` at `0x1800e79be`

## pseudocode

```c
PRTL_USER_PROCESS_PARAMETERS __fastcall BasepCreateProcessParameters(
        const WCHAR *a1,
        __int128 *a2,
        const WCHAR *a3,
        const WCHAR *a4,
        const WCHAR *a5,
        const WCHAR *a6,
        char a7,
        __int64 a8,
        __int64 a9,
        int a10,
        int a11,
        int a12,
        __int64 a13,
        __int64 a14)
{
  struct _PEB *v17; // r15
  __int128 v18; // xmm0
  NTSTATUS inited; // ebx
  char v20; // si
  const WCHAR *v21; // rdx
  int DllDirectory; // eax
  struct _RTL_USER_PROCESS_PARAMETERS *v24; // rcx
  struct _RTL_USER_PROCESS_PARAMETERS *v25; // rcx
  PRTL_USER_PROCESS_PARAMETERS ProcessParameters; // [rsp+20h] [rbp-E0h] BYREF
  PCWSTR SourceString; // [rsp+28h] [rbp-D8h]
  PCWSTR v28; // [rsp+30h] [rbp-D0h]
  _BYTE v29[56]; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING v30; // [rsp+78h] [rbp-88h] BYREF
  struct _UNICODE_STRING v31; // [rsp+90h] [rbp-70h] BYREF
  __int128 v32; // [rsp+A0h] [rbp-60h]
  struct _UNICODE_STRING DestinationString; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v34; // [rsp+C0h] [rbp-40h]
  struct _UNICODE_STRING v35; // [rsp+F0h] [rbp-10h] BYREF
  struct _UNICODE_STRING v36; // [rsp+100h] [rbp+0h] BYREF
  struct _UNICODE_STRING v37; // [rsp+110h] [rbp+10h] BYREF
  __int16 v38; // [rsp+120h] [rbp+20h]
  __int16 v39; // [rsp+122h] [rbp+22h]
  __int64 v40; // [rsp+128h] [rbp+28h]
  struct _UNICODE_STRING v41; // [rsp+450h] [rbp+350h] BYREF

  v28 = a1;
  SourceString = a6;
  ProcessParameters = 0;
  memset_0(v29, 0, 0x450u);
  v17 = NtCurrentPeb();
  v18 = *a2;
  v34 = a8;
  v32 = v18;
  inited = RtlInitUnicodeStringEx(&DestinationString, a4);
  if ( inited < 0 )
    goto LABEL_26;
  inited = RtlInitUnicodeStringEx(&v30, a3);
  if ( inited < 0 )
    goto LABEL_26;
  inited = RtlInitUnicodeStringEx(&v41, SourceString);
  if ( inited < 0 )
    goto LABEL_26;
  inited = RtlInitUnicodeStringEx(&v31, a5);
  if ( inited < 0 )
    goto LABEL_26;
  v20 = 0;
  if ( a5 || a7 || (a12 & 0x10000) != 0 )
    goto LABEL_6;
  DllDirectory = LdrGetDllDirectory(&v31);
  if ( v31.Length <= 2u || DllDirectory != -1073741789 )
  {
    RtlInitUnicodeString(&v31, 0);
    goto LABEL_6;
  }
  v31.Buffer = (PWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v31.Length);
  if ( !v31.Buffer )
  {
    inited = -1073741801;
    goto LABEL_26;
  }
  v31.MaximumLength = v31.Length;
  inited = LdrGetDllDirectory(&v31);
  if ( inited >= 0 )
  {
    v20 = 1;
LABEL_6:
    inited = RtlInitUnicodeStringEx(&v36, *(PCWSTR *)(a9 + 16));
    if ( inited >= 0 )
    {
      inited = RtlInitUnicodeStringEx(&v37, *(PCWSTR *)(a9 + 8));
      if ( inited >= 0 )
      {
        v21 = *(const WCHAR **)(a9 + 24);
        v40 = *(_QWORD *)(a9 + 72);
        v38 = *(_WORD *)(a9 + 66);
        v39 = v38;
        if ( !v21 )
          v21 = v28;
        inited = RtlInitUnicodeStringEx(&v35, v21);
        if ( inited >= 0 )
        {
          inited = RtlCreateProcessParametersWithTemplate(&ProcessParameters, v29, 1);
          if ( inited >= 0 )
          {
            ProcessParameters->StartingX = *(_DWORD *)(a9 + 32);
            ProcessParameters->StartingY = *(_DWORD *)(a9 + 36);
            ProcessParameters->CountX = *(_DWORD *)(a9 + 40);
            ProcessParameters->CountY = *(_DWORD *)(a9 + 44);
            ProcessParameters->CountCharsX = *(_DWORD *)(a9 + 48);
            ProcessParameters->CountCharsY = *(_DWORD *)(a9 + 52);
            ProcessParameters->FillAttribute = *(_DWORD *)(a9 + 56);
            ProcessParameters->WindowFlags = *(_DWORD *)(a9 + 60);
            ProcessParameters->ShowWindowFlags = *(unsigned __int16 *)(a9 + 64);
            if ( (a10 & 0x200) != 0 )
              ProcessParameters[1].Flags = 0;
            else
              ProcessParameters[1].Flags = v17->ProcessParameters[1].Flags;
            if ( (*(_DWORD *)(a9 + 60) & 0x700) != 0 )
            {
              if ( a14 || (*(_DWORD *)(a9 + 60) & 0x100) == 0 || (a12 & 4) != 0 )
              {
                ProcessParameters->StandardInput = *(HANDLE *)(a9 + 80);
                ProcessParameters->StandardOutput = *(HANDLE *)(a9 + 88);
                ProcessParameters->StandardError = *(HANDLE *)(a9 + 96);
              }
              else
              {
                ProcessParameters->StandardInput = 0;
                ProcessParameters->StandardOutput = 0;
                ProcessParameters->StandardError = 0;
              }
            }
            if ( (a10 & 8) != 0 )
            {
              ProcessParameters->ConsoleHandle = (HANDLE)-1LL;
            }
            else if ( (a10 & 0x10) != 0 )
            {
              ProcessParameters->ConsoleHandle = (HANDLE)-2LL;
            }
            else if ( (a10 & 0x8000000) != 0 )
            {
              ProcessParameters->ConsoleHandle = (HANDLE)-3LL;
            }
            else
            {
              if ( a13 && *(_QWORD *)a13 )
              {
                ProcessParameters->ConsoleHandle = **(HANDLE **)a13;
                ProcessParameters->ConsoleFlags |= 2u;
                if ( *(_BYTE *)(a13 + 8) )
                  ProcessParameters->ConsoleFlags |= 4u;
              }
              else
              {
                ProcessParameters->ConsoleHandle = (HANDLE)xmmword_1803A30D0;
                if ( !ProcessParameters->ConsoleHandle )
                  ProcessParameters->ConsoleHandle = v17->ProcessParameters->ConsoleHandle;
              }
              if ( (*(_DWORD *)(a9 + 60) & 0x700) == 0 && a11 )
              {
                v24 = v17->ProcessParameters;
                if ( (v24->WindowFlags & 0x200) == 0 )
                  ProcessParameters->StandardInput = v24->StandardInput;
                v25 = v17->ProcessParameters;
                if ( (v25->WindowFlags & 0x400) == 0 )
                  ProcessParameters->StandardOutput = v25->StandardOutput;
                ProcessParameters->StandardError = v17->ProcessParameters->StandardError;
              }
            }
            if ( (a10 & 0x200) != 0 && (a10 & 0x10) == 0 )
              ProcessParameters->ConsoleFlags |= 1u;
            ProcessParameters->Flags |= v17->ProcessParameters->Flags & 0x100;
            if ( v20 )
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v31.Buffer);
            return ProcessParameters;
          }
        }
      }
    }
  }
LABEL_26:
  if ( ProcessParameters )
    RtlDestroyProcessParameters(ProcessParameters);
  BaseSetLastNTError((unsigned int)inited);
  return 0;
}

```

## disassembly

```asm
0x1800e7570  push    rbp
0x1800e7572  push    rbx
0x1800e7573  push    rsi
0x1800e7574  push    rdi
0x1800e7575  push    r12
0x1800e7577  push    r13
0x1800e7579  push    r14
0x1800e757b  push    r15
0x1800e757d  lea     rbp, [rsp-3A8h]
0x1800e7585  sub     rsp, 4A8h
0x1800e758c  mov     rax, cs:__security_cookie
0x1800e7593  xor     rax, rsp
0x1800e7596  mov     [rbp+3E0h+var_50], rax
0x1800e759d  mov     rax, [rbp+3E0h+arg_28]
0x1800e75a4  mov     r13, r8
0x1800e75a7  mov     r12, [rbp+3E0h+arg_20]
0x1800e75ae  mov     rdi, rdx
0x1800e75b1  mov     rbx, [rbp+3E0h+arg_38]
0x1800e75b8  xor     edx, edx; Val
0x1800e75ba  mov     r14, [rbp+3E0h+arg_40]
0x1800e75c1  mov     r8d, 450h; Size
0x1800e75c7  mov     [rsp+4E0h+var_4B0], rcx
0x1800e75cc  mov     rsi, r9
0x1800e75cf  lea     rcx, [rsp+4E0h+var_4A0]; void *
0x1800e75d4  mov     [rsp+4E0h+SourceString], rax
0x1800e75d9  mov     [rsp+4E0h+ProcessParameters], 0
0x1800e75e2  call    memset_0
0x1800e75e7  mov     r15, gs:60h
0x1800e75f0  lea     rcx, [rbp+3E0h+DestinationString]; DestinationString
0x1800e75f4  movups  xmm0, xmmword ptr [rdi]
0x1800e75f7  mov     rdx, rsi; SourceString
0x1800e75fa  mov     [rbp+3E0h+var_420], rbx
0x1800e75fe  movdqu  [rbp+3E0h+var_440], xmm0
0x1800e7603  call    cs:__imp_RtlInitUnicodeStringEx
0x1800e7609  mov     ebx, eax
0x1800e760b  test    eax, eax
0x1800e760d  js      loc_1800E7876
0x1800e7613  mov     rdx, r13; SourceString
0x1800e7616  lea     rcx, [rsp+4E0h+var_468]; DestinationString
0x1800e761b  call    cs:__imp_RtlInitUnicodeStringEx
0x1800e7621  xor     r13d, r13d
0x1800e7624  mov     ebx, eax
0x1800e7626  test    eax, eax
0x1800e7628  js      loc_1800E7876
0x1800e762e  mov     rdx, [rsp+4E0h+SourceString]; SourceString
0x1800e7633  lea     rcx, [rbp+3E0h+var_90]; DestinationString
0x1800e763a  call    cs:__imp_RtlInitUnicodeStringEx
0x1800e7640  mov     ebx, eax
0x1800e7642  test    eax, eax
0x1800e7644  js      loc_1800E7876
0x1800e764a  mov     rdx, r12; SourceString
0x1800e764d  lea     rcx, [rbp+3E0h+var_450]; DestinationString
0x1800e7651  call    cs:__imp_RtlInitUnicodeStringEx
0x1800e7657  mov     ebx, eax
0x1800e7659  test    eax, eax
0x1800e765b  js      loc_1800E7876
0x1800e7661  mov     edi, [rbp+3E0h+arg_58]
0x1800e7667  mov     sil, r13b
0x1800e766a  lea     ebx, [r13+2]
0x1800e766e  test    r12, r12
0x1800e7671  jz      loc_1800E783A
0x1800e7677  mov     rdx, [r14+10h]; SourceString
0x1800e767b  lea     rcx, [rbp+3E0h+var_3E0]; DestinationString
0x1800e767f  call    cs:__imp_RtlInitUnicodeStringEx
0x1800e7685  mov     ebx, eax
0x1800e7687  test    eax, eax
0x1800e7689  js      loc_1800E7876
0x1800e768f  mov     rdx, [r14+8]; SourceString
0x1800e7693  lea     rcx, [rbp+3E0h+var_3D0]; DestinationString
0x1800e7697  call    cs:__imp_RtlInitUnicodeStringEx
0x1800e769d  mov     ebx, eax
0x1800e769f  test    eax, eax
0x1800e76a1  js      loc_1800E7876
0x1800e76a7  mov     rax, [r14+48h]
0x1800e76ab  lea     rcx, [rbp+3E0h+var_3F0]; DestinationString
0x1800e76af  mov     rdx, [r14+18h]
0x1800e76b3  mov     [rbp+3E0h+var_3B8], rax
0x1800e76b7  movzx   eax, word ptr [r14+42h]
0x1800e76bc  mov     [rbp+3E0h+var_3C0], ax
0x1800e76c0  mov     [rbp+3E0h+var_3BE], ax
0x1800e76c4  test    rdx, rdx
0x1800e76c7  jnz     short loc_1800E76CE
0x1800e76c9  mov     rdx, [rsp+4E0h+var_4B0]; SourceString
0x1800e76ce  call    cs:__imp_RtlInitUnicodeStringEx
0x1800e76d4  mov     ebx, eax
0x1800e76d6  test    eax, eax
0x1800e76d8  js      loc_1800E7876
0x1800e76de  mov     r8d, 1
0x1800e76e4  lea     rdx, [rsp+4E0h+var_4A0]
0x1800e76e9  lea     rcx, [rsp+4E0h+ProcessParameters]
0x1800e76ee  call    cs:__imp_RtlCreateProcessParametersWithTemplate
0x1800e76f4  mov     ebx, eax
0x1800e76f6  test    eax, eax
0x1800e76f8  js      loc_1800E7876
0x1800e76fe  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800e7703  mov     ebx, 200h
0x1800e7708  mov     ecx, [r14+20h]
0x1800e770c  mov     r8d, [rbp+3E0h+arg_48]
0x1800e7713  mov     r9d, r8d
0x1800e7716  mov     [rax+88h], ecx
0x1800e771c  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800e7721  mov     ecx, [r14+24h]
0x1800e7725  mov     [rax+8Ch], ecx
0x1800e772b  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800e7730  mov     ecx, [r14+28h]
0x1800e7734  mov     [rax+90h], ecx
0x1800e773a  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800e773f  mov     ecx, [r14+2Ch]
0x1800e7743  mov     [rax+94h], ecx
0x1800e7749  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800e774e  mov     ecx, [r14+30h]
0x1800e7752  mov     [rax+98h], ecx
0x1800e7758  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800e775d  mov     ecx, [r14+34h]
0x1800e7761  mov     [rax+9Ch], ecx
0x1800e7767  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800e776c  mov     ecx, [r14+38h]
0x1800e7770  mov     [rax+0A0h], ecx
0x1800e7776  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800e777b  mov     ecx, [r14+3Ch]
0x1800e777f  mov     [rax+0A4h], ecx
0x1800e7785  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800e778a  movzx   ecx, word ptr [r14+40h]
0x1800e778f  mov     [rax+0A8h], ecx
0x1800e7795  and     r9d, ebx
0x1800e7798  jnz     loc_1800E79F1
0x1800e779e  mov     rax, [r15+20h]
0x1800e77a2  mov     ecx, [rax+408h]
0x1800e77a8  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800e77ad  mov     [rax+408h], ecx
0x1800e77b3  mov     r10d, 700h
0x1800e77b9  mov     r11d, 100h
0x1800e77bf  test    [r14+3Ch], r10d
0x1800e77c3  jnz     loc_1800E794E
0x1800e77c9  mov     edx, r8d
0x1800e77cc  and     edx, 10h
0x1800e77cf  test    r8b, 8
0x1800e77d3  jnz     loc_1800E793C
0x1800e77d9  test    edx, edx
0x1800e77db  jz      loc_1800E788F
0x1800e77e1  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800e77e6  mov     qword ptr [rax+10h], 0FFFFFFFFFFFFFFFEh
0x1800e77ee  test    r9d, r9d
0x1800e77f1  jnz     loc_1800E7A81
0x1800e77f7  mov     rax, [r15+20h]
0x1800e77fb  mov     rdx, [rsp+4E0h+ProcessParameters]
0x1800e7800  mov     ecx, [rax+8]
0x1800e7803  and     ecx, r11d
0x1800e7806  or      [rdx+8], ecx
0x1800e7809  test    sil, sil
0x1800e780c  jnz     loc_1800E7A02
0x1800e7812  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800e7817  mov     rcx, [rbp+3E0h+var_50]
0x1800e781e  xor     rcx, rsp; StackCookie
0x1800e7821  call    __security_check_cookie
0x1800e7826  add     rsp, 4A8h
0x1800e782d  pop     r15
0x1800e782f  pop     r14
0x1800e7831  pop     r13
0x1800e7833  pop     r12
0x1800e7835  pop     rdi
0x1800e7836  pop     rsi
0x1800e7837  pop     rbx
0x1800e7838  pop     rbp
0x1800e7839  retn
0x1800e783a  cmp     [rbp+3E0h+arg_30], r13b
0x1800e7841  jnz     loc_1800E7677
0x1800e7847  bt      edi, 10h
0x1800e784b  jb      loc_1800E7677
0x1800e7851  lea     rcx, [rbp+3E0h+var_450]
0x1800e7855  call    cs:__imp_LdrGetDllDirectory
0x1800e785b  cmp     [rbp+3E0h+var_450.Length], bx
0x1800e785f  ja      loc_1800E799F
0x1800e7865  xor     edx, edx; SourceString
0x1800e7867  lea     rcx, [rbp+3E0h+var_450]; DestinationString
0x1800e786b  call    cs:__imp_RtlInitUnicodeString
0x1800e7871  jmp     loc_1800E7677
0x1800e7876  mov     rcx, [rsp+4E0h+ProcessParameters]; ProcessParameters
0x1800e787b  test    rcx, rcx
0x1800e787e  jnz     loc_1800E7A97
0x1800e7884  mov     ecx, ebx
0x1800e7886  call    BaseSetLastNTError
0x1800e788b  xor     eax, eax
0x1800e788d  jmp     short loc_1800E7817
0x1800e788f  bt      r8d, 1Bh
0x1800e7894  jb      loc_1800E798D
0x1800e789a  mov     r8, [rbp+3E0h+arg_60]
0x1800e78a1  test    r8, r8
0x1800e78a4  jz      short loc_1800E78B2
0x1800e78a6  mov     rcx, [r8]
0x1800e78a9  test    rcx, rcx
0x1800e78ac  jnz     loc_1800E7A54
0x1800e78b2  mov     rcx, [rsp+4E0h+ProcessParameters]
0x1800e78b7  mov     rax, qword ptr cs:xmmword_1803A30D0
0x1800e78be  mov     [rcx+10h], rax
0x1800e78c2  mov     r8, [rsp+4E0h+ProcessParameters]
0x1800e78c7  cmp     [r8+10h], r13
0x1800e78cb  jnz     short loc_1800E78D9
0x1800e78cd  mov     rax, [r15+20h]
0x1800e78d1  mov     rcx, [rax+10h]
0x1800e78d5  mov     [r8+10h], rcx
0x1800e78d9  test    [r14+3Ch], r10d
0x1800e78dd  jnz     loc_1800E77EE
0x1800e78e3  cmp     [rbp+3E0h+arg_50], r13d
0x1800e78ea  jz      loc_1800E77EE
0x1800e78f0  mov     rcx, [r15+20h]
0x1800e78f4  test    [rcx+0A4h], ebx
0x1800e78fa  jnz     short loc_1800E7909
0x1800e78fc  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800e7901  mov     rcx, [rcx+20h]
0x1800e7905  mov     [rax+20h], rcx
0x1800e7909  mov     rcx, [r15+20h]
0x1800e790d  test    dword ptr [rcx+0A4h], 400h
0x1800e7917  jnz     short loc_1800E7926
0x1800e7919  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800e791e  mov     rcx, [rcx+28h]
0x1800e7922  mov     [rax+28h], rcx
0x1800e7926  mov     rax, [r15+20h]
0x1800e792a  mov     rcx, [rax+30h]
0x1800e792e  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800e7933  mov     [rax+30h], rcx
0x1800e7937  jmp     loc_1800E77EE
0x1800e793c  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800e7941  mov     qword ptr [rax+10h], 0FFFFFFFFFFFFFFFFh
0x1800e7949  jmp     loc_1800E77EE
0x1800e794e  cmp     [rbp+3E0h+arg_68], r13
0x1800e7955  jnz     short loc_1800E7961
0x1800e7957  test    [r14+3Ch], r11d
0x1800e795b  jnz     loc_1800E7A2A
0x1800e7961  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800e7966  mov     rcx, [r14+50h]
0x1800e796a  mov     [rax+20h], rcx
0x1800e796e  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800e7973  mov     rcx, [r14+58h]
0x1800e7977  mov     [rax+28h], rcx
0x1800e797b  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800e7980  mov     rcx, [r14+60h]
0x1800e7984  mov     [rax+30h], rcx
0x1800e7988  jmp     loc_1800E77C9
0x1800e798d  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800e7992  mov     qword ptr [rax+10h], 0FFFFFFFFFFFFFFFDh
0x1800e799a  jmp     loc_1800E77EE
0x1800e799f  cmp     eax, 0C0000023h
0x1800e79a4  jnz     loc_1800E7865
0x1800e79aa  mov     rcx, gs:60h
0x1800e79b3  xor     edx, edx; Flags
0x1800e79b5  movzx   r8d, [rbp+3E0h+var_450.Length]; Size
0x1800e79ba  mov     rcx, [rcx+30h]; HeapHandle
0x1800e79be  call    cs:__imp_RtlAllocateHeap
0x1800e79c4  mov     [rbp+3E0h+var_450.Buffer], rax
0x1800e79c8  test    rax, rax
0x1800e79cb  jz      short loc_1800E7A20
0x1800e79cd  movzx   eax, [rbp+3E0h+var_450.Length]
0x1800e79d1  lea     rcx, [rbp+3E0h+var_450]
0x1800e79d5  mov     [rbp+3E0h+var_450.MaximumLength], ax
0x1800e79d9  call    cs:__imp_LdrGetDllDirectory
0x1800e79df  mov     ebx, eax
0x1800e79e1  test    eax, eax
0x1800e79e3  js      loc_1800E7876
0x1800e79e9  mov     sil, 1
0x1800e79ec  jmp     loc_1800E7677
0x1800e79f1  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800e79f6  mov     [rax+408h], r13d
0x1800e79fd  jmp     loc_1800E77B3
0x1800e7a02  mov     rcx, gs:60h
0x1800e7a0b  xor     edx, edx; Flags
0x1800e7a0d  mov     r8, [rbp+3E0h+var_450.Buffer]; P
0x1800e7a11  mov     rcx, [rcx+30h]; HeapHandle
0x1800e7a15  call    cs:__imp_RtlFreeHeap
0x1800e7a1b  jmp     loc_1800E7812
0x1800e7a20  mov     ebx, 0C0000017h
0x1800e7a25  jmp     loc_1800E7876
0x1800e7a2a  test    dil, 4
0x1800e7a2e  jnz     loc_1800E7961
0x1800e7a34  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800e7a39  mov     [rax+20h], r13
0x1800e7a3d  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800e7a42  mov     [rax+28h], r13
0x1800e7a46  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800e7a4b  mov     [rax+30h], r13
0x1800e7a4f  jmp     loc_1800E77C9
0x1800e7a54  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800e7a59  mov     rcx, [rcx]
0x1800e7a5c  mov     [rax+10h], rcx
0x1800e7a60  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800e7a65  or      dword ptr [rax+18h], 2
0x1800e7a69  cmp     [r8+8], r13b
0x1800e7a6d  jz      loc_1800E78D9
0x1800e7a73  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800e7a78  or      dword ptr [rax+18h], 4
0x1800e7a7c  jmp     loc_1800E78D9
0x1800e7a81  test    edx, edx
0x1800e7a83  jnz     loc_1800E77F7
0x1800e7a89  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800e7a8e  or      dword ptr [rax+18h], 1
0x1800e7a92  jmp     loc_1800E77F7
0x1800e7a97  call    cs:__imp_RtlDestroyProcessParameters
0x1800e7a9d  jmp     loc_1800E7884
```
