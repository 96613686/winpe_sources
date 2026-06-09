# AhgGenomeGetManifest

- ea: `0x18001101c`
- end: `0x180011233`
- name: `AhgGenomeGetManifest`
- size: `535`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180010d10`

## callees

- `0x18001101c`
- `0x180011924`
- `0x180011e94`
- `0x18001207c`
- `0x180015220`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800111bb`
- `ntdll!RtlFreeHeap` at `0x1800111bb`
- `KERNEL32!GetLastError` at `0x18001109b`
- `KERNEL32!GetLastError` at `0x18001109b`
- `KERNEL32!ReleaseActCtx` at `0x18001121f`
- `KERNEL32!ReleaseActCtx` at `0x18001121f`
- `KERNEL32!CreateActCtxW` at `0x180011071`
- `KERNEL32!CreateActCtxW` at `0x18001108c`
- `KERNEL32!CreateActCtxW` at `0x180011071`
- `KERNEL32!CreateActCtxW` at `0x18001108c`

## string_xrefs

- `0x1800110ae`: `AhgGenomeGetManifest`
- `0x1800110e9`: `AhgGenomeGetManifest`
- `0x18001116e`: `AhgGenomeGetManifest`
- `0x180011203`: `AhgGenomeGetManifest`
- `0x1800110a1`: `Failed to create activation context [%d]`
- `0x18001115c`: `Failed to set data for attribute AHG_TAG_MANIFEST_SUPPORTED_OS`
- `0x1800110d8`: `Failed to get supported OS from application manifest [%d]`
- `0x1800111f6`: `No UAC manifest`
- `0x180011182`: `Failed to read run level information [%d]`
- `0x180011193`: `AhgManifestReadRunLevel`

## pseudocode

```c
__int64 __fastcall AhgGenomeGetManifest(const WCHAR *a1)
{
  HANDLE v2; // rdi
  DWORD LastError; // ebx
  int v4; // eax
  PVOID v5; // rbx
  int v6; // r14d
  const char *v7; // r9
  __int64 v8; // r8
  ACTCTXW pActCtx; // [rsp+30h] [rbp-40h] BYREF
  int v11; // [rsp+A0h] [rbp+30h] BYREF
  PVOID P; // [rsp+A8h] [rbp+38h] BYREF
  int v13; // [rsp+B0h] [rbp+40h] BYREF

  pActCtx.lpSource = a1;
  LODWORD(P) = 0;
  v11 = 0;
  v13 = 0;
  *(_OWORD *)&pActCtx.wProcessorArchitecture = 0;
  pActCtx.cbSize = 56;
  *(_OWORD *)&pActCtx.lpApplicationName = 0;
  pActCtx.lpResourceName = (LPCWSTR)1;
  pActCtx.dwFlags = 8;
  v2 = CreateActCtxW(&pActCtx);
  if ( v2 != (HANDLE)-1LL || (pActCtx.lpResourceName = (LPCWSTR)2, v2 = CreateActCtxW(&pActCtx), v2 != (HANDLE)-1LL) )
  {
    if ( (unsigned int)AhgManifestReadSupportedOs(&P, v2) )
    {
      AslLogCallPrintf(3, "AhgGenomeGetManifest", 654, "Failed to get supported OS from application manifest [%d]");
    }
    else
    {
      v13 = WORD1(P) + ((unsigned __int16)P << 16);
      if ( !(unsigned int)AhgpSetAttribute(a1 + 388, 16, &v13) )
      {
        v7 = "Failed to set data for attribute AHG_TAG_MANIFEST_SUPPORTED_OS";
        v8 = 664;
LABEL_11:
        LastError = 87;
        AslLogCallPrintf(1, "AhgGenomeGetManifest", v8, v7);
LABEL_21:
        ReleaseActCtx(v2);
        return LastError;
      }
    }
    v11 = 0;
    P = 0;
    v4 = AhgpManifestRead(&P, v2, 5u);
    v5 = P;
    v6 = v4;
    if ( v4 || !P )
      AslLogCallPrintf(3, "AhgManifestReadRunLevel", 286, "Failed to read run level information [%d]");
    else
      v11 = *((_DWORD *)P + 1);
    if ( v5 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
    if ( v6 || !v11 )
    {
      AslLogCallPrintf(3, "AhgGenomeGetManifest", 672, "No UAC manifest");
    }
    else if ( !(unsigned int)AhgpSetAttribute(a1 + 396, 17, &v11) )
    {
      v7 = "Failed to set data for attribute AHG_TAG_UAC_RUN_LEVEL";
      v8 = 680;
      goto LABEL_11;
    }
    LastError = 0;
    goto LABEL_21;
  }
  LastError = GetLastError();
  AslLogCallPrintf(2, "AhgGenomeGetManifest", 648, "Failed to create activation context [%d]");
  return LastError;
}

```

## disassembly

```asm
0x18001101c  push    rbp
0x18001101e  push    rbx
0x18001101f  push    rdi
0x180011020  push    r14
0x180011022  push    r15
0x180011024  mov     rbp, rsp
0x180011027  sub     rsp, 70h
0x18001102b  mov     r15, rcx
0x18001102e  mov     [rbp+pActCtx.lpSource], rcx
0x180011032  xorps   xmm0, xmm0
0x180011035  mov     dword ptr [rbp+P], 0
0x18001103c  xorps   xmm1, xmm1
0x18001103f  mov     [rbp+arg_0], 0
0x180011046  lea     rcx, [rbp+pActCtx]; pActCtx
0x18001104a  mov     [rbp+arg_10], 0
0x180011051  movdqu  xmmword ptr [rbp+pActCtx.wProcessorArchitecture], xmm0
0x180011056  mov     [rbp+pActCtx.cbSize], 38h ; '8'
0x18001105d  movdqu  xmmword ptr [rbp+pActCtx.lpApplicationName], xmm1
0x180011062  mov     [rbp+pActCtx.lpResourceName], 1
0x18001106a  mov     [rbp+pActCtx.dwFlags], 8
0x180011071  call    cs:__imp_CreateActCtxW
0x180011077  mov     rdi, rax
0x18001107a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001107e  jnz     short loc_1800110C8
0x180011080  lea     r14d, [rax+3]
0x180011084  lea     rcx, [rbp+pActCtx]; pActCtx
0x180011088  mov     [rbp+pActCtx.lpResourceName], r14
0x18001108c  call    cs:__imp_CreateActCtxW
0x180011092  mov     rdi, rax
0x180011095  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180011099  jnz     short loc_1800110C8
0x18001109b  call    cs:__imp_GetLastError
0x1800110a1  lea     r9, aFailedToCreate; "Failed to create activation context [%d"...
0x1800110a8  mov     r8d, 288h
0x1800110ae  lea     rdx, aAhggenomegetma; "AhgGenomeGetManifest"
0x1800110b5  mov     [rsp+70h+var_50], eax
0x1800110b9  mov     ecx, r14d
0x1800110bc  mov     ebx, eax
0x1800110be  call    AslLogCallPrintf
0x1800110c3  jmp     loc_180011225
0x1800110c8  mov     rdx, rdi
0x1800110cb  lea     rcx, [rbp+P]
0x1800110cf  call    AhgManifestReadSupportedOs
0x1800110d4  test    eax, eax
0x1800110d6  jz      short loc_180011133
0x1800110d8  lea     r9, aFailedToGetSup; "Failed to get supported OS from applica"...
0x1800110df  mov     [rsp+70h+var_50], eax
0x1800110e3  mov     r8d, 28Eh
0x1800110e9  lea     rdx, aAhggenomegetma; "AhgGenomeGetManifest"
0x1800110f0  mov     ecx, 3
0x1800110f5  call    AslLogCallPrintf
0x1800110fa  mov     r8d, 5
0x180011100  mov     [rbp+arg_0], 0
0x180011107  mov     rdx, rdi
0x18001110a  mov     [rbp+P], 0
0x180011112  lea     rcx, [rbp+P]
0x180011116  call    AhgpManifestRead
0x18001111b  mov     rbx, [rbp+P]
0x18001111f  mov     r14d, eax
0x180011122  test    eax, eax
0x180011124  jnz     short loc_180011182
0x180011126  test    rbx, rbx
0x180011129  jz      short loc_180011182
0x18001112b  mov     eax, [rbx+4]
0x18001112e  mov     [rbp+arg_0], eax
0x180011131  jmp     short loc_1800111A4
0x180011133  movzx   eax, word ptr [rbp+P+2]
0x180011137  lea     rcx, [r15+308h]
0x18001113e  movzx   edx, word ptr [rbp+P]
0x180011142  lea     r8, [rbp+arg_10]
0x180011146  shl     edx, 10h
0x180011149  add     edx, eax
0x18001114b  mov     [rbp+arg_10], edx
0x18001114e  mov     edx, 10h
0x180011153  call    AhgpSetAttribute
0x180011158  test    eax, eax
0x18001115a  jnz     short loc_1800110FA
0x18001115c  lea     r9, aFailedToSetDat; "Failed to set data for attribute AHG_TA"...
0x180011163  mov     r8d, 298h
0x180011169  mov     ebx, 57h ; 'W'
0x18001116e  lea     rdx, aAhggenomegetma; "AhgGenomeGetManifest"
0x180011175  lea     ecx, [rbx-56h]
0x180011178  call    AslLogCallPrintf
0x18001117d  jmp     loc_180011216
0x180011182  lea     r9, aFailedToReadRu; "Failed to read run level information [%"...
0x180011189  mov     [rsp+70h+var_50], eax
0x18001118d  mov     r8d, 11Eh
0x180011193  lea     rdx, aAhgmanifestrea_0; "AhgManifestReadRunLevel"
0x18001119a  mov     ecx, 3
0x18001119f  call    AslLogCallPrintf
0x1800111a4  test    rbx, rbx
0x1800111a7  jz      short loc_1800111C1
0x1800111a9  mov     rcx, gs:60h
0x1800111b2  mov     r8, rbx; P
0x1800111b5  xor     edx, edx; Flags
0x1800111b7  mov     rcx, [rcx+30h]; HeapHandle
0x1800111bb  call    cs:__imp_RtlFreeHeap
0x1800111c1  test    r14d, r14d
0x1800111c4  jnz     short loc_1800111F6
0x1800111c6  cmp     [rbp+arg_0], r14d
0x1800111ca  jz      short loc_1800111F6
0x1800111cc  lea     edx, [r14+11h]
0x1800111d0  lea     rcx, [r15+318h]
0x1800111d7  lea     r8, [rbp+arg_0]
0x1800111db  call    AhgpSetAttribute
0x1800111e0  test    eax, eax
0x1800111e2  jnz     short loc_180011214
0x1800111e4  lea     r9, aFailedToSetDat_0; "Failed to set data for attribute AHG_TA"...
0x1800111eb  mov     r8d, 2A8h
0x1800111f1  jmp     loc_180011169
0x1800111f6  lea     r9, aNoUacManifest; "No UAC manifest"
0x1800111fd  mov     r8d, 2A0h
0x180011203  lea     rdx, aAhggenomegetma; "AhgGenomeGetManifest"
0x18001120a  mov     ecx, 3
0x18001120f  call    AslLogCallPrintf
0x180011214  xor     ebx, ebx
0x180011216  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18001121a  jz      short loc_180011225
0x18001121c  mov     rcx, rdi; hActCtx
0x18001121f  call    cs:__imp_ReleaseActCtx
0x180011225  mov     eax, ebx
0x180011227  add     rsp, 70h
0x18001122b  pop     r15
0x18001122d  pop     r14
0x18001122f  pop     rdi
0x180011230  pop     rbx
0x180011231  pop     rbp
0x180011232  retn
```
