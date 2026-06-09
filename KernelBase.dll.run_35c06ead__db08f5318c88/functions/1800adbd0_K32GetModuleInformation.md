# K32GetModuleInformation

- ea: `0x1800adbd0`
- end: `0x1800ade47`
- name: `K32GetModuleInformation`
- size: `631`
- prototype: `BOOL __stdcall(HANDLE hProcess, HMODULE hModule, LPMODULEINFO lpmodinfo, DWORD cb)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x1800134a0`
- `0x180037714`
- `0x1800adbd0`
- `0x1800ade50`
- `0x18012d119`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800adda6`
- `ntdll!RtlNtStatusToDosError` at `0x1800ade31`
- `ntdll!RtlNtStatusToDosError` at `0x1800adda6`
- `ntdll!RtlNtStatusToDosError` at `0x1800ade31`
- `ntdll!NtQueryInformationProcess` at `0x1800adc63`
- `ntdll!NtQueryInformationProcess` at `0x1800adc63`
- `ntdll!NtReadVirtualMemory` at `0x1800adca2`
- `ntdll!NtReadVirtualMemory` at `0x1800adce2`
- `ntdll!NtReadVirtualMemory` at `0x1800add2d`
- `ntdll!NtReadVirtualMemory` at `0x1800ade05`
- `ntdll!NtReadVirtualMemory` at `0x1800adca2`
- `ntdll!NtReadVirtualMemory` at `0x1800adce2`
- `ntdll!NtReadVirtualMemory` at `0x1800add2d`
- `ntdll!NtReadVirtualMemory` at `0x1800ade05`

## pseudocode

```c
BOOL __stdcall K32GetModuleInformation(HANDLE hProcess, HMODULE hModule, LPMODULEINFO lpmodinfo, DWORD cb)
{
  int InformationProcess; // eax
  __int64 v9; // rbx
  NTSTATUS v10; // eax
  __int64 v11; // rdi
  int v12; // ebx
  __int64 v13; // rax
  ULONG v14; // ecx
  ULONG_PTR NumberOfBytesRead; // [rsp+30h] [rbp-138h] BYREF
  HMODULE v17; // [rsp+38h] [rbp-130h] BYREF
  __int64 v18; // [rsp+40h] [rbp-128h] BYREF
  __int64 Buffer; // [rsp+48h] [rbp-120h] BYREF
  __int128 v20; // [rsp+50h] [rbp-118h]
  _OWORD ProcessInformation[3]; // [rsp+68h] [rbp-100h] BYREF
  _BYTE v22[16]; // [rsp+A0h] [rbp-C8h] BYREF
  __int64 v23; // [rsp+B0h] [rbp-B8h]
  HMODULE v24; // [rsp+D0h] [rbp-98h]
  void *v25; // [rsp+D8h] [rbp-90h]
  int v26; // [rsp+E0h] [rbp-88h]
  __int16 v27; // [rsp+10Ch] [rbp-5Ch]

  memset_0(v22, 0, 0x88u);
  v20 = 0;
  if ( cb < 0x18 )
  {
    v14 = 122;
  }
  else
  {
    v17 = hModule;
    memset(ProcessInformation, 0, 44);
    Buffer = 0;
    v18 = 0;
    InformationProcess = NtQueryInformationProcess(hProcess, ProcessBasicInformation, ProcessInformation, 0x30u, 0);
    if ( InformationProcess < 0 )
    {
      v14 = RtlNtStatusToDosError(InformationProcess);
    }
    else
    {
      v9 = *((_QWORD *)&ProcessInformation[0] + 1);
      if ( !v17 )
      {
        NumberOfBytesRead = 0;
        v10 = NtReadVirtualMemory(
                hProcess,
                (PVOID)(*((_QWORD *)&ProcessInformation[0] + 1) + 16LL),
                &v17,
                8u,
                &NumberOfBytesRead);
        if ( v10 < 0 )
          goto LABEL_16;
      }
      NumberOfBytesRead = 0;
      v10 = NtReadVirtualMemory(hProcess, (PVOID)(v9 + 24), &Buffer, 8u, &NumberOfBytesRead);
      if ( v10 < 0 )
        goto LABEL_16;
      if ( Buffer )
      {
        v11 = Buffer + 32;
        NumberOfBytesRead = 0;
        v10 = NtReadVirtualMemory(hProcess, (PVOID)(Buffer + 32), &v18, 8u, &NumberOfBytesRead);
        if ( v10 >= 0 )
        {
          v12 = 0;
          v13 = v18;
          while ( v13 != v11 )
          {
            NumberOfBytesRead = 0;
            v10 = NtReadVirtualMemory(hProcess, (PVOID)(v13 - 16), v22, 0x88u, &NumberOfBytesRead);
            if ( v10 < 0 )
              goto LABEL_16;
            if ( v24 == v17 )
            {
              if ( !v27 )
                return 0;
              goto LABEL_14;
            }
            v13 = v23;
            v18 = v23;
            if ( (unsigned int)++v12 > 0x2710 )
              goto LABEL_12;
          }
          if ( (unsigned int)Wow64FindModuleEx(hProcess) )
          {
LABEL_14:
            *(_QWORD *)&v20 = hModule;
            DWORD2(v20) = v26;
            *(_OWORD *)&lpmodinfo->lpBaseOfDll = v20;
            lpmodinfo->EntryPoint = v25;
            return 1;
          }
          return 0;
        }
LABEL_16:
        BaseSetLastNTError((unsigned int)v10);
        return 0;
      }
LABEL_12:
      v14 = 6;
    }
  }
  SetLastError_0(v14);
  return 0;
}

```

## disassembly

```asm
0x1800adbd0  mov     [rsp+arg_18], rbx; GetModuleInformation
0x1800adbd5  push    rsi
0x1800adbd6  push    rdi
0x1800adbd7  push    r12
0x1800adbd9  push    r14
0x1800adbdb  push    r15
0x1800adbdd  sub     rsp, 140h
0x1800adbe4  mov     rax, cs:__security_cookie
0x1800adbeb  xor     rax, rsp
0x1800adbee  mov     [rsp+168h+var_38], rax
0x1800adbf6  mov     ebx, r9d
0x1800adbf9  mov     r14, r8
0x1800adbfc  mov     r15, rdx
0x1800adbff  mov     rsi, rcx
0x1800adc02  xor     edx, edx; Val
0x1800adc04  mov     r8d, 88h; Size
0x1800adc0a  lea     rcx, [rsp+168h+var_C8]; void *
0x1800adc12  call    memset_0
0x1800adc17  xorps   xmm0, xmm0
0x1800adc1a  xor     eax, eax
0x1800adc1c  movups  [rsp+168h+var_118], xmm0
0x1800adc21  cmp     ebx, 18h
0x1800adc24  jb      loc_1800ADE40
0x1800adc2a  mov     [rsp+168h+var_130], r15
0x1800adc2f  movups  [rsp+168h+ProcessInformation], xmm0
0x1800adc34  movups  xmmword ptr [rsp+168h+var_F0], xmm0
0x1800adc39  movups  xmmword ptr [rsp+168h+var_F0+0Ch], xmm0
0x1800adc41  xor     r12d, r12d
0x1800adc44  mov     [rsp+168h+Buffer], r12
0x1800adc49  mov     [rsp+168h+var_128], r12
0x1800adc4e  mov     [rsp+168h+ReturnLength], r12; ReturnLength
0x1800adc53  mov     r9d, 30h ; '0'; ProcessInformationLength
0x1800adc59  lea     r8, [rsp+168h+ProcessInformation]; ProcessInformation
0x1800adc5e  xor     edx, edx; ProcessInformationClass
0x1800adc60  mov     rcx, rsi; ProcessHandle
0x1800adc63  call    cs:__imp_NtQueryInformationProcess
0x1800adc69  test    eax, eax
0x1800adc6b  js      loc_1800ADE2F
0x1800adc71  mov     rbx, qword ptr [rsp+168h+ProcessInformation+8]
0x1800adc76  cmp     [rsp+168h+var_130], r12
0x1800adc7b  jz      loc_1800ADDE4
0x1800adc81  mov     [rsp+168h+NumberOfBytesRead], r12
0x1800adc86  lea     rdx, [rbx+18h]; BaseAddress
0x1800adc8a  lea     rax, [rsp+168h+NumberOfBytesRead]
0x1800adc8f  mov     [rsp+168h+ReturnLength], rax; NumberOfBytesRead
0x1800adc94  mov     r9d, 8; NumberOfBytesToRead
0x1800adc9a  lea     r8, [rsp+168h+Buffer]; Buffer
0x1800adc9f  mov     rcx, rsi; ProcessHandle
0x1800adca2  call    cs:__imp_NtReadVirtualMemory
0x1800adca8  test    eax, eax
0x1800adcaa  js      loc_1800ADE13
0x1800adcb0  mov     rdi, [rsp+168h+Buffer]
0x1800adcb5  test    rdi, rdi
0x1800adcb8  jz      loc_1800ADD61
0x1800adcbe  add     rdi, 20h ; ' '
0x1800adcc2  mov     [rsp+168h+NumberOfBytesRead], r12
0x1800adcc7  lea     rax, [rsp+168h+NumberOfBytesRead]
0x1800adccc  mov     [rsp+168h+ReturnLength], rax; NumberOfBytesRead
0x1800adcd1  mov     r9d, 8; NumberOfBytesToRead
0x1800adcd7  lea     r8, [rsp+168h+var_128]; Buffer
0x1800adcdc  mov     rdx, rdi; BaseAddress
0x1800adcdf  mov     rcx, rsi; ProcessHandle
0x1800adce2  call    cs:__imp_NtReadVirtualMemory
0x1800adce8  test    eax, eax
0x1800adcea  js      loc_1800ADE13
0x1800adcf0  mov     ebx, r12d
0x1800adcf3  mov     rdx, [rsp+168h+var_130]
0x1800adcf8  mov     rax, [rsp+168h+var_128]
0x1800adcfd  nop     dword ptr [rax]
0x1800add00  lea     r8, [rsp+168h+var_C8]; Buffer
0x1800add08  mov     rcx, rsi; ProcessHandle
0x1800add0b  cmp     rax, rdi
0x1800add0e  jz      loc_1800ADE1E
0x1800add14  mov     [rsp+168h+NumberOfBytesRead], r12
0x1800add19  lea     rdx, [rax-10h]; BaseAddress
0x1800add1d  lea     rax, [rsp+168h+NumberOfBytesRead]
0x1800add22  mov     [rsp+168h+ReturnLength], rax; NumberOfBytesRead
0x1800add27  mov     r9d, 88h; NumberOfBytesToRead
0x1800add2d  call    cs:__imp_NtReadVirtualMemory
0x1800add33  test    eax, eax
0x1800add35  js      loc_1800ADE13
0x1800add3b  mov     rdx, [rsp+168h+var_130]
0x1800add40  cmp     [rsp+168h+var_98], rdx
0x1800add48  jz      short loc_1800ADD6B
0x1800add4a  mov     rax, [rsp+168h+var_B8]
0x1800add52  mov     [rsp+168h+var_128], rax
0x1800add57  inc     ebx
0x1800add59  cmp     ebx, 2710h
0x1800add5f  jbe     short loc_1800ADD00
0x1800add61  mov     ecx, 6
0x1800add66  jmp     loc_1800ADE39
0x1800add6b  cmp     [rsp+168h+var_5C], r12w
0x1800add74  jz      loc_1800ADE2B
0x1800add7a  mov     qword ptr [rsp+168h+var_118], r15
0x1800add7f  mov     eax, [rsp+168h+var_88]
0x1800add86  mov     dword ptr [rsp+168h+var_118+8], eax
0x1800add8a  movups  xmm0, [rsp+168h+var_118]
0x1800add8f  movups  xmmword ptr [r14], xmm0
0x1800add93  movsd   xmm1, [rsp+168h+var_90]
0x1800add9c  movsd   qword ptr [r14+10h], xmm1
0x1800adda2  jmp     short loc_1800ADDB7
0x1800adda4  mov     ecx, eax; Status
0x1800adda6  call    cs:__imp_RtlNtStatusToDosError
0x1800addac  mov     ecx, eax; dwErrCode
0x1800addae  call    SetLastError_0
0x1800addb3  xor     eax, eax
0x1800addb5  jmp     short loc_1800ADDBC
0x1800addb7  mov     eax, 1
0x1800addbc  mov     rcx, [rsp+168h+var_38]
0x1800addc4  xor     rcx, rsp; StackCookie
0x1800addc7  call    __security_check_cookie
0x1800addcc  mov     rbx, [rsp+168h+arg_18]
0x1800addd4  add     rsp, 140h
0x1800adddb  pop     r15
0x1800adddd  pop     r14
0x1800adddf  pop     r12
0x1800adde1  pop     rdi
0x1800adde2  pop     rsi
0x1800adde3  retn
0x1800adde4  mov     [rsp+168h+NumberOfBytesRead], r12
0x1800adde9  lea     rdx, [rbx+10h]; BaseAddress
0x1800added  lea     rax, [rsp+168h+NumberOfBytesRead]
0x1800addf2  mov     [rsp+168h+ReturnLength], rax; NumberOfBytesRead
0x1800addf7  mov     r9d, 8; NumberOfBytesToRead
0x1800addfd  lea     r8, [rsp+168h+var_130]; Buffer
0x1800ade02  mov     rcx, rsi; ProcessHandle
0x1800ade05  call    cs:__imp_NtReadVirtualMemory
0x1800ade0b  test    eax, eax
0x1800ade0d  jns     loc_1800ADC81
0x1800ade13  mov     ecx, eax
0x1800ade15  call    BaseSetLastNTError
0x1800ade1a  xor     eax, eax
0x1800ade1c  jmp     short loc_1800ADDBC
0x1800ade1e  call    Wow64FindModuleEx
0x1800ade23  test    eax, eax
0x1800ade25  jnz     loc_1800ADD7A
0x1800ade2b  xor     eax, eax
0x1800ade2d  jmp     short loc_1800ADDBC
0x1800ade2f  mov     ecx, eax; Status
0x1800ade31  call    cs:__imp_RtlNtStatusToDosError
0x1800ade37  mov     ecx, eax; dwErrCode
0x1800ade39  call    SetLastError_0
0x1800ade3e  jmp     short loc_1800ADE2B
0x1800ade40  mov     ecx, 7Ah ; 'z'
0x1800ade45  jmp     short loc_1800ADE39
```
