# SdbSetPermLayerKeys

- ea: `0x180046f10`
- end: `0x1800470f7`
- name: `SdbSetPermLayerKeys`
- size: `487`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003b6c0`
- `0x180047130`

## callees

- `0x18000f114`
- `0x180016910`
- `0x18003d070`
- `0x180046c40`
- `0x180046f10`
- `0x1800591b0`

## import_xrefs

- `ntdll!NtSetValueKey` at `0x18004708b`
- `ntdll!NtSetValueKey` at `0x18004708b`
- `ntdll!NtClose` at `0x18004700d`
- `ntdll!NtClose` at `0x180047098`
- `ntdll!NtClose` at `0x18004700d`
- `ntdll!NtClose` at `0x180047098`
- `ntdll!RtlInitUnicodeString` at `0x180047057`
- `ntdll!RtlInitUnicodeString` at `0x180047057`

## string_xrefs

- `0x180046f99`: `\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`
- `0x18004701a`: `\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Layers`
- `0x180046fe3`: `Failed to create user key path for "%ws" [%x]`
- `0x180047039`: `Failed to create user key path "%ws" [%x]`
- `0x180046f77`: `Failed to get perm layer path`

## pseudocode

```c
__int64 __fastcall SdbSetPermLayerKeys(_WORD *a1, _WORD *a2, int a3)
{
  unsigned int v5; // ebp
  int v6; // eax
  int Key; // eax
  __int64 v8; // rax
  NTSTATUS v9; // edi
  ULONG DataSize; // [rsp+28h] [rbp-270h]
  ULONG DataSizea; // [rsp+28h] [rbp-270h]
  HANDLE Handle; // [rsp+30h] [rbp-268h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-260h] BYREF
  WCHAR SourceString[264]; // [rsp+50h] [rbp-248h] BYREF

  Handle = 0;
  DestinationString = 0;
  if ( !a2 || !*a2 )
    return SdbDeletePermLayerKeys(a1, a3);
  v5 = 0;
  if ( (int)AslPathBuildSignature((__int64)SourceString, 0x104u, (__int64)a1) >= 0 )
  {
    if ( (int)AslRegistryGetKey(
                &Handle,
                L"\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags",
                0x20119u,
                a3,
                0) >= 0
      || (v6 = AslRegistryGetKey(
                 &Handle,
                 L"\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags",
                 0,
                 a3,
                 1),
          v6 >= 0) )
    {
      NtClose(Handle);
      Key = AslRegistryGetKey(
              &Handle,
              L"\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\Layers",
              0,
              a3,
              1);
      if ( Key >= 0 )
      {
        RtlInitUnicodeString(&DestinationString, SourceString);
        v8 = -1;
        do
          ++v8;
        while ( a2[v8] );
        v9 = NtSetValueKey(Handle, &DestinationString, 0, 1u, a2, 2 * v8 + 2);
        NtClose(Handle);
        if ( v9 >= 0 )
          return 1;
        else
          AslLogCallPrintf(1, "SdbSetPermLayerKeys", 203, "Failed NtSetValueKey [%x]", v9);
      }
      else
      {
        DataSizea = Key;
        AslLogCallPrintf(
          1,
          "SdbSetPermLayerKeys",
          185,
          "Failed to create user key path \"%ws\" [%x]",
          L"\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\Layers",
          DataSizea);
      }
    }
    else
    {
      DataSize = v6;
      AslLogCallPrintf(
        1,
        "SdbSetPermLayerKeys",
        173,
        "Failed to create user key path for \"%ws\" [%x]",
        L"\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags",
        DataSize);
    }
  }
  else
  {
    AslLogCallPrintf(1, "SdbSetPermLayerKeys", 161, "Failed to get perm layer path");
  }
  return v5;
}

```

## disassembly

```asm
0x180046f10  mov     [rsp+arg_18], rbx
0x180046f15  push    rbp
0x180046f16  push    rsi
0x180046f17  push    rdi
0x180046f18  push    r14
0x180046f1a  push    r15
0x180046f1c  sub     rsp, 270h
0x180046f23  mov     rax, cs:__security_cookie
0x180046f2a  xor     rax, rsp
0x180046f2d  mov     [rsp+298h+var_38], rax
0x180046f35  xor     r14d, r14d
0x180046f38  xorps   xmm0, xmm0
0x180046f3b  mov     [rsp+298h+Handle], r14
0x180046f40  mov     edi, r8d
0x180046f43  mov     rsi, rdx
0x180046f46  movups  xmmword ptr [rsp+298h+DestinationString.Length], xmm0
0x180046f4b  test    rdx, rdx
0x180046f4e  jz      loc_1800470C9
0x180046f54  cmp     [rdx], r14w
0x180046f58  jz      loc_1800470C9
0x180046f5e  mov     r8, rcx
0x180046f61  mov     edx, 104h
0x180046f66  lea     rcx, [rsp+298h+SourceString]
0x180046f6b  mov     ebp, r14d
0x180046f6e  call    AslPathBuildSignature
0x180046f73  test    eax, eax
0x180046f75  jns     short loc_180046F99
0x180046f77  lea     r9, aFailedToGetPer; "Failed to get perm layer path"
0x180046f7e  mov     r8d, 0A1h
0x180046f84  lea     rdx, aSdbsetpermlaye_1; "SdbSetPermLayerKeys"
0x180046f8b  lea     ecx, [r14+1]
0x180046f8f  call    AslLogCallPrintf
0x180046f94  jmp     loc_1800470C5
0x180046f99  lea     r15, aSoftwareMicros; "\\Software\\Microsoft\\Windows NT\\Curr"...
0x180046fa0  mov     dword ptr [rsp+298h+Data], r14d
0x180046fa5  mov     rdx, r15
0x180046fa8  lea     rcx, [rsp+298h+Handle]
0x180046fad  mov     r9d, edi
0x180046fb0  mov     r8d, 20119h
0x180046fb6  call    AslRegistryGetKey
0x180046fbb  mov     ebx, 1
0x180046fc0  test    eax, eax
0x180046fc2  jns     short loc_180047008
0x180046fc4  mov     r9d, edi
0x180046fc7  mov     dword ptr [rsp+298h+Data], ebx
0x180046fcb  xor     r8d, r8d
0x180046fce  lea     rcx, [rsp+298h+Handle]
0x180046fd3  mov     rdx, r15
0x180046fd6  call    AslRegistryGetKey
0x180046fdb  test    eax, eax
0x180046fdd  jns     short loc_180047008
0x180046fdf  mov     [rsp+298h+DataSize], eax
0x180046fe3  lea     r9, aFailedToCreate_14; "Failed to create user key path for \"%w"...
0x180046fea  mov     [rsp+298h+Data], r15
0x180046fef  mov     r8d, 0ADh
0x180046ff5  lea     rdx, aSdbsetpermlaye_1; "SdbSetPermLayerKeys"
0x180046ffc  mov     ecx, ebx
0x180046ffe  call    AslLogCallPrintf
0x180047003  jmp     loc_1800470C5
0x180047008  mov     rcx, [rsp+298h+Handle]; Handle
0x18004700d  call    cs:__imp_NtClose
0x180047013  mov     r9d, edi
0x180047016  mov     dword ptr [rsp+298h+Data], ebx
0x18004701a  lea     rdi, aSoftwareMicros_2; "\\Software\\Microsoft\\Windows NT\\Curr"...
0x180047021  xor     r8d, r8d
0x180047024  mov     rdx, rdi
0x180047027  lea     rcx, [rsp+298h+Handle]
0x18004702c  call    AslRegistryGetKey
0x180047031  test    eax, eax
0x180047033  jns     short loc_18004704D
0x180047035  mov     [rsp+298h+DataSize], eax
0x180047039  lea     r9, aFailedToCreate_0; "Failed to create user key path \"%ws\" "...
0x180047040  mov     [rsp+298h+Data], rdi
0x180047045  mov     r8d, 0B9h
0x18004704b  jmp     short loc_180046FF5
0x18004704d  lea     rdx, [rsp+298h+SourceString]; SourceString
0x180047052  lea     rcx, [rsp+298h+DestinationString]; DestinationString
0x180047057  call    cs:__imp_RtlInitUnicodeString
0x18004705d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180047061  inc     rax
0x180047064  cmp     [rsi+rax*2], r14w
0x180047069  jnz     short loc_180047061
0x18004706b  mov     rcx, [rsp+298h+Handle]; KeyHandle
0x180047070  lea     eax, ds:2[rax*2]
0x180047077  mov     [rsp+298h+DataSize], eax; DataSize
0x18004707b  lea     rdx, [rsp+298h+DestinationString]; ValueName
0x180047080  mov     r9d, ebx; Type
0x180047083  mov     [rsp+298h+Data], rsi; Data
0x180047088  xor     r8d, r8d; TitleIndex
0x18004708b  call    cs:__imp_NtSetValueKey
0x180047091  mov     rcx, [rsp+298h+Handle]; Handle
0x180047096  mov     edi, eax
0x180047098  call    cs:__imp_NtClose
0x18004709e  test    edi, edi
0x1800470a0  jns     short loc_1800470C3
0x1800470a2  lea     r9, aFailedNtsetval; "Failed NtSetValueKey [%x]"
0x1800470a9  mov     dword ptr [rsp+298h+Data], edi
0x1800470ad  mov     r8d, 0CBh
0x1800470b3  lea     rdx, aSdbsetpermlaye_1; "SdbSetPermLayerKeys"
0x1800470ba  mov     ecx, ebx
0x1800470bc  call    AslLogCallPrintf
0x1800470c1  jmp     short loc_1800470C5
0x1800470c3  mov     ebp, ebx
0x1800470c5  mov     eax, ebp
0x1800470c7  jmp     short loc_1800470D0
0x1800470c9  mov     edx, edi
0x1800470cb  call    SdbDeletePermLayerKeys
0x1800470d0  mov     rcx, [rsp+298h+var_38]
0x1800470d8  xor     rcx, rsp; StackCookie
0x1800470db  call    __security_check_cookie
0x1800470e0  mov     rbx, [rsp+298h+arg_18]
0x1800470e8  add     rsp, 270h
0x1800470ef  pop     r15
0x1800470f1  pop     r14
0x1800470f3  pop     rdi
0x1800470f4  pop     rsi
0x1800470f5  pop     rbp
0x1800470f6  retn
```
