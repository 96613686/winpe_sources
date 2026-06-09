# AhgManifestReadSupportedOs

- ea: `0x180011e94`
- end: `0x180012075`
- name: `AhgManifestReadSupportedOs`
- size: `481`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18001101c`

## callees

- `0x180011e94`
- `0x18001207c`
- `0x180015220`
- `0x18001623a`
- `0x180016280`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180012045`
- `ntdll!RtlFreeHeap` at `0x180012045`
- `KERNEL32!GetVersionExW` at `0x180011f40`
- `KERNEL32!GetVersionExW` at `0x180011f40`
- `KERNEL32!GetLastError` at `0x180011f4a`
- `KERNEL32!GetLastError` at `0x180011f4a`

## string_xrefs

- `0x180011f02`: `Failed to read manifest [%d]`
- `0x180012012`: `No manifest to read`
- `0x180011f14`: `AhgManifestReadSupportedOs`
- `0x18001201f`: `AhgManifestReadSupportedOs`

## pseudocode

```c
__int64 __fastcall AhgManifestReadSupportedOs(_WORD *a1, void *a2)
{
  unsigned int v4; // eax
  unsigned int *v5; // rbx
  unsigned int v6; // edi
  const char *v7; // r9
  __int64 v8; // r8
  __int64 v9; // rcx
  DWORD LastError; // eax
  int v11; // r8d
  unsigned int v12; // r10d
  unsigned int v13; // edx
  unsigned int i; // ebp
  __int64 v15; // rcx
  unsigned int v16; // r9d
  __int64 v17; // r11
  unsigned int v18; // r9d
  PVOID P[2]; // [rsp+30h] [rbp-158h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+40h] [rbp-148h] BYREF

  P[0] = 0;
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  v4 = AhgpManifestRead(P, a2, 6u);
  v5 = (unsigned int *)P[0];
  v6 = v4;
  if ( v4 )
  {
    v7 = "Failed to read manifest [%d]";
    v8 = 187;
    v9 = 2;
LABEL_3:
    AslLogCallPrintf(v9, "AhgManifestReadSupportedOs", v8, v7);
    goto LABEL_21;
  }
  if ( P[0] && *(_DWORD *)P[0] )
  {
    if ( !GetVersionExW(&VersionInformation) )
    {
      LastError = GetLastError();
      v7 = "GetVersionEx failed [%d]";
      v8 = 203;
      v6 = LastError;
      v9 = 1;
      goto LABEL_3;
    }
    v11 = 0;
    v12 = 0;
    v13 = LOWORD(VersionInformation.dwMinorVersion) + (LOWORD(VersionInformation.dwMajorVersion) << 16);
    v6 = 2;
    for ( i = v13; v12 < *v5; ++v12 )
    {
      v15 = 8LL * v12;
      if ( v5[v15 + 6] == 1 )
      {
        v16 = 0;
        while ( 1 )
        {
          v17 = 4LL * v16;
          if ( *(_QWORD *)&v5[v15 + 2] == *(__int64 *)((char *)&SbSupportedOsList[v17] + 4)
            && *(_QWORD *)&v5[v15 + 4] == *(__int64 *)((char *)&SbSupportedOsList[v17 + 1] + 4) )
          {
            break;
          }
          if ( ++v16 >= 5 )
            goto LABEL_18;
        }
        v18 = HIWORD(SbSupportedOsList[v17 + 2]) + (WORD2(SbSupportedOsList[v17 + 2]) << 16);
        if ( v18 <= i && i - v18 < v13 )
        {
          v6 = 0;
          v13 = i - v18;
          v11 = HIWORD(SbSupportedOsList[v17 + 2]) + (WORD2(SbSupportedOsList[v17 + 2]) << 16);
        }
      }
LABEL_18:
      ;
    }
    a1[1] = (unsigned __int8)v11;
    *a1 = BYTE2(v11);
  }
  else
  {
    v6 = 2;
    AslLogCallPrintf(3, "AhgManifestReadSupportedOs", 193, "No manifest to read");
  }
LABEL_21:
  if ( v5 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
  return v6;
}

```

## disassembly

```asm
0x180011e94  mov     [rsp+arg_10], rbx
0x180011e99  mov     [rsp+arg_18], rbp
0x180011e9e  push    rsi
0x180011e9f  push    rdi
0x180011ea0  push    r15
0x180011ea2  sub     rsp, 170h
0x180011ea9  mov     rax, cs:__security_cookie
0x180011eb0  xor     rax, rsp
0x180011eb3  mov     [rsp+188h+var_28], rax
0x180011ebb  mov     rbx, rdx
0x180011ebe  mov     [rsp+188h+P], 0
0x180011ec7  mov     rsi, rcx
0x180011eca  xor     edx, edx; Val
0x180011ecc  lea     rcx, [rsp+188h+VersionInformation.dwMajorVersion]; void *
0x180011ed1  mov     r8d, 118h; Size
0x180011ed7  call    memset_0
0x180011edc  mov     r8d, 6
0x180011ee2  mov     [rsp+188h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x180011eea  mov     rdx, rbx
0x180011eed  lea     rcx, [rsp+188h+P]
0x180011ef2  call    AhgpManifestRead
0x180011ef7  mov     rbx, [rsp+188h+P]
0x180011efc  mov     edi, eax
0x180011efe  test    eax, eax
0x180011f00  jz      short loc_180011F29
0x180011f02  lea     r9, aFailedToReadMa; "Failed to read manifest [%d]"
0x180011f09  mov     r8d, 0BBh
0x180011f0f  mov     ecx, 2
0x180011f14  lea     rdx, aAhgmanifestrea; "AhgManifestReadSupportedOs"
0x180011f1b  mov     [rsp+188h+var_168], eax
0x180011f1f  call    AslLogCallPrintf
0x180011f24  jmp     loc_18001202E
0x180011f29  test    rbx, rbx
0x180011f2c  jz      loc_18001200D
0x180011f32  cmp     dword ptr [rbx], 0
0x180011f35  jz      loc_18001200D
0x180011f3b  lea     rcx, [rsp+188h+VersionInformation]; lpVersionInformation
0x180011f40  call    cs:__imp_GetVersionExW
0x180011f46  test    eax, eax
0x180011f48  jnz     short loc_180011F66
0x180011f4a  call    cs:__imp_GetLastError
0x180011f50  lea     r9, aGetversionexFa; "GetVersionEx failed [%d]"
0x180011f57  mov     r8d, 0CBh
0x180011f5d  mov     edi, eax
0x180011f5f  mov     ecx, 1
0x180011f64  jmp     short loc_180011F14
0x180011f66  movzx   edx, word ptr [rsp+188h+VersionInformation.dwMajorVersion]
0x180011f6b  xor     r8d, r8d
0x180011f6e  movzx   eax, word ptr [rsp+188h+VersionInformation.dwMinorVersion]
0x180011f73  xor     r10d, r10d
0x180011f76  shl     edx, 10h
0x180011f79  add     edx, eax
0x180011f7b  lea     edi, [r8+2]
0x180011f7f  mov     ebp, edx
0x180011f81  cmp     [rbx], r8d
0x180011f84  jbe     short loc_180011FF8
0x180011f86  lea     r15, SbSupportedOsList
0x180011f8d  mov     ecx, r10d
0x180011f90  shl     rcx, 5
0x180011f94  cmp     dword ptr [rcx+rbx+18h], 1
0x180011f99  jnz     short loc_180011FF0
0x180011f9b  xor     r9d, r9d
0x180011f9e  mov     rax, [rcx+rbx+8]
0x180011fa3  mov     r11d, r9d
0x180011fa6  shl     r11, 5
0x180011faa  cmp     rax, [r11+r15+4]
0x180011faf  jnz     short loc_180011FBD
0x180011fb1  mov     rax, [rcx+rbx+10h]
0x180011fb6  cmp     rax, [r11+r15+0Ch]
0x180011fbb  jz      short loc_180011FC8
0x180011fbd  inc     r9d
0x180011fc0  cmp     r9d, 5
0x180011fc4  jb      short loc_180011F9E
0x180011fc6  jmp     short loc_180011FF0
0x180011fc8  movzx   r9d, word ptr [r11+r15+14h]
0x180011fce  movzx   eax, word ptr [r11+r15+16h]
0x180011fd4  shl     r9d, 10h
0x180011fd8  add     r9d, eax
0x180011fdb  cmp     r9d, ebp
0x180011fde  ja      short loc_180011FF0
0x180011fe0  mov     eax, ebp
0x180011fe2  sub     eax, r9d
0x180011fe5  cmp     eax, edx
0x180011fe7  jnb     short loc_180011FF0
0x180011fe9  xor     edi, edi
0x180011feb  mov     edx, eax
0x180011fed  mov     r8d, r9d
0x180011ff0  inc     r10d
0x180011ff3  cmp     r10d, [rbx]
0x180011ff6  jb      short loc_180011F8D
0x180011ff8  movzx   eax, r8b
0x180011ffc  shr     r8d, 10h
0x180012000  mov     [rsi+2], ax
0x180012004  movzx   eax, r8b
0x180012008  mov     [rsi], ax
0x18001200b  jmp     short loc_18001202E
0x18001200d  mov     edi, 2
0x180012012  lea     r9, aNoManifestToRe; "No manifest to read"
0x180012019  mov     r8d, 0C1h
0x18001201f  lea     rdx, aAhgmanifestrea; "AhgManifestReadSupportedOs"
0x180012026  lea     ecx, [rdi+1]
0x180012029  call    AslLogCallPrintf
0x18001202e  test    rbx, rbx
0x180012031  jz      short loc_18001204B
0x180012033  mov     rcx, gs:60h
0x18001203c  mov     r8, rbx; P
0x18001203f  xor     edx, edx; Flags
0x180012041  mov     rcx, [rcx+30h]; HeapHandle
0x180012045  call    cs:__imp_RtlFreeHeap
0x18001204b  mov     eax, edi
0x18001204d  mov     rcx, [rsp+188h+var_28]
0x180012055  xor     rcx, rsp; StackCookie
0x180012058  call    __security_check_cookie
0x18001205d  lea     r11, [rsp+188h+var_18]
0x180012065  mov     rbx, [r11+30h]
0x180012069  mov     rbp, [r11+38h]
0x18001206d  mov     rsp, r11
0x180012070  pop     r15
0x180012072  pop     rdi
0x180012073  pop     rsi
0x180012074  retn
```
