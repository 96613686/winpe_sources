# telemetryutil::etl::EnsureDirectoryExists(ushort const *)

- ea: `0x18004fbb4`
- end: `0x18004fef3`
- name: `?EnsureDirectoryExists@etl@telemetryutil@@YAJPEBG@Z`
- size: `831`
- prototype: `signed int __fastcall(LPCWSTR lpFileName, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x18004fa60`

## callees

- `0x1800023d8`
- `0x18001def0`
- `0x18004fbb4`
- `0x1800502c2`
- `0x180050300`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18004fda7`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18004fea6`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18004fda7`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18004fea6`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18004fc28`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18004fd91`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18004fe94`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18004fc28`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18004fd91`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18004fe94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fdb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004feb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fdb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004feb0`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
signed int __fastcall telemetryutil::etl::EnsureDirectoryExists(LPCWSTR lpFileName, const unsigned __int16 *a2)
{
  signed int result; // eax
  DWORD FileAttributesW; // eax
  unsigned __int64 v5; // r8
  WCHAR *p_FileName; // rcx
  __int64 v7; // rax
  __int64 v8; // r9
  WCHAR *v9; // rdx
  unsigned __int64 i; // rax
  __int16 v11; // cx
  __int64 v12; // rdx
  WCHAR *v13; // rax
  unsigned __int64 v14; // rbx
  unsigned __int64 v15; // rdi
  __int16 v16; // ax
  DWORD v17; // eax
  unsigned __int64 v18; // rax
  DWORD v19; // eax
  __int16 v20; // [rsp+1Eh] [rbp-E2h]
  WCHAR FileName; // [rsp+20h] [rbp-E0h] BYREF
  __int16 v22; // [rsp+22h] [rbp-DEh]
  __int16 v23; // [rsp+24h] [rbp-DCh]

  if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl) )
    return -2147024846;
  if ( !lpFileName )
    return -2147467261;
  if ( !*lpFileName )
    return -2147024809;
  FileAttributesW = GetFileAttributesW(lpFileName);
  if ( FileAttributesW != -1 )
  {
    if ( (FileAttributesW & 0x10) == 0 )
      return -2147024629;
    return 0;
  }
  memset_0(&FileName, 0, 0x800u);
  v5 = 2;
  p_FileName = &FileName;
  v7 = 2147483646;
  v8 = 1024;
  do
  {
    if ( !v7 )
      break;
    if ( !*lpFileName )
      break;
    *p_FileName++ = *lpFileName++;
    --v7;
    --v8;
  }
  while ( v8 );
  v9 = p_FileName - 1;
  result = v8 == 0 ? 0x8007007A : 0;
  if ( v8 )
    v9 = p_FileName;
  *v9 = 0;
  if ( v8 )
  {
    for ( i = 0; i < 0x400; ++i )
    {
      v11 = *(&FileName + i);
      if ( !v11 )
        break;
      if ( v11 == 47 )
        *(&FileName + i) = 92;
    }
    v12 = 1024;
    v13 = &FileName;
    do
    {
      if ( !*v13 )
        break;
      ++v13;
      --v12;
    }
    while ( v12 );
    result = v12 == 0 ? 0x80070057 : 0;
    v14 = (1024 - v12) & ((unsigned __int128)-(__int128)(unsigned __int64)v12 >> 64);
    if ( v12 )
    {
      v15 = 3;
      if ( v14 )
      {
        while ( 1 )
        {
          if ( *(&v20 + v14) != 92 )
            goto LABEL_43;
          v16 = v22;
          if ( v14 != 3 )
            goto LABEL_31;
          if ( v22 == 58 )
            break;
LABEL_34:
          --v14;
          if ( 2 * v14 >= 0x800 )
LABEL_75:
            _report_rangecheckfailure();
          *(&FileName + v14) = 0;
          if ( !v14 )
            goto LABEL_36;
        }
        if ( v23 == 92 )
          goto LABEL_44;
LABEL_31:
        if ( v14 == 2 && FileName == 92 && v22 == 92 )
          goto LABEL_46;
        goto LABEL_34;
      }
LABEL_43:
      v16 = v22;
      if ( v14 >= 2 )
      {
LABEL_44:
        if ( FileName == 92 && v16 == 92 )
        {
LABEL_46:
          if ( v14 > 2 )
          {
            do
            {
              if ( *(&FileName + v5) == 92 )
                break;
              ++v5;
            }
            while ( v5 < v14 );
          }
          v18 = v5 + 1;
          if ( v5 >= v14 )
            v18 = v5;
          while ( v18 < v14 && *(&FileName + v18) != 92 )
            ++v18;
          v15 = v18 + 1;
          if ( v18 >= v14 )
            v15 = v18;
          goto LABEL_73;
        }
      }
      if ( v14 < 3 || v16 != 58 || v23 != 92 )
      {
        v15 = 0;
        if ( v14 )
          v15 = FileName == 92;
      }
LABEL_73:
      while ( v15 < v14 )
      {
        if ( *(&FileName + v15) == 92 )
        {
          if ( 2 * v15 >= 0x800 )
            goto LABEL_75;
          *(&FileName + v15) = 0;
          v19 = GetFileAttributesW(&FileName);
          if ( v19 == -1 )
          {
            if ( !CreateDirectoryW(&FileName, 0) )
            {
              result = GetLastError();
              if ( result != 183 )
                goto LABEL_68;
            }
          }
          else if ( (v19 & 0x10) == 0 )
          {
            return -2147024629;
          }
          *(&FileName + v15) = 92;
        }
        ++v15;
      }
LABEL_36:
      if ( FileName )
      {
        v17 = GetFileAttributesW(&FileName);
        if ( v17 != -1 && (v17 & 0x10) != 0 )
          return 0;
      }
      if ( CreateDirectoryW(&FileName, 0) )
        return 0;
      result = GetLastError();
      if ( result == 183 )
        return 0;
LABEL_68:
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18004fbb4  mov     [rsp-8+arg_8], rbx
0x18004fbb9  mov     [rsp-8+arg_10], rsi
0x18004fbbe  push    rbp
0x18004fbbf  push    rdi
0x18004fbc0  push    r12
0x18004fbc2  push    r14
0x18004fbc4  push    r15
0x18004fbc6  lea     rbp, [rsp-730h]
0x18004fbce  sub     rsp, 830h
0x18004fbd5  mov     rax, cs:__security_cookie
0x18004fbdc  xor     rax, rsp
0x18004fbdf  mov     [rbp+750h+var_30], rax
0x18004fbe6  mov     rbx, rcx
0x18004fbe9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl(void)'::`2'::impl
0x18004fbf0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(void)
0x18004fbf5  xor     r14d, r14d
0x18004fbf8  test    al, al
0x18004fbfa  jnz     short loc_18004FC06
0x18004fbfc  mov     eax, 80070032h
0x18004fc01  jmp     loc_18004FDC4
0x18004fc06  test    rbx, rbx
0x18004fc09  jnz     short loc_18004FC15
0x18004fc0b  mov     eax, 80004003h
0x18004fc10  jmp     loc_18004FDC4
0x18004fc15  cmp     [rbx], r14w
0x18004fc19  jnz     short loc_18004FC25
0x18004fc1b  mov     eax, 80070057h
0x18004fc20  jmp     loc_18004FDC4
0x18004fc25  mov     rcx, rbx; lpFileName
0x18004fc28  call    cs:__imp_GetFileAttributesW
0x18004fc2e  cmp     eax, 0FFFFFFFFh
0x18004fc31  jz      short loc_18004FC45
0x18004fc33  test    al, 10h
0x18004fc35  jnz     loc_18004FDC2
0x18004fc3b  mov     eax, 8007010Bh
0x18004fc40  jmp     loc_18004FDC4
0x18004fc45  mov     esi, 800h
0x18004fc4a  lea     rcx, [rsp+850h+FileName]; void *
0x18004fc4f  mov     r8d, esi; Size
0x18004fc52  xor     edx, edx; Val
0x18004fc54  call    memset_0
0x18004fc59  mov     r8d, 2
0x18004fc5f  lea     rcx, [rsp+850h+FileName]
0x18004fc64  mov     r10d, 400h
0x18004fc6a  mov     eax, 7FFFFFFEh
0x18004fc6f  mov     r9d, r10d
0x18004fc72  lea     r12d, [r8-1]
0x18004fc76  test    rax, rax
0x18004fc79  jz      short loc_18004FC94
0x18004fc7b  movzx   edx, word ptr [rbx]
0x18004fc7e  test    dx, dx
0x18004fc81  jz      short loc_18004FC94
0x18004fc83  mov     [rcx], dx
0x18004fc86  add     rbx, r8
0x18004fc89  add     rcx, r8
0x18004fc8c  sub     rax, r12
0x18004fc8f  sub     r9, r12
0x18004fc92  jnz     short loc_18004FC76
0x18004fc94  mov     rax, r9
0x18004fc97  lea     rdx, [rcx-2]
0x18004fc9b  neg     rax
0x18004fc9e  sbb     eax, eax
0x18004fca0  not     eax
0x18004fca2  and     eax, 8007007Ah
0x18004fca7  test    r9, r9
0x18004fcaa  cmovnz  rdx, rcx
0x18004fcae  mov     [rdx], r14w
0x18004fcb2  jz      loc_18004FDC4
0x18004fcb8  mov     rax, r14
0x18004fcbb  mov     r15d, 5Ch ; '\'
0x18004fcc1  movzx   ecx, [rsp+rax*2+850h+FileName]
0x18004fcc6  test    cx, cx
0x18004fcc9  jz      short loc_18004FCDF
0x18004fccb  cmp     cx, 2Fh ; '/'
0x18004fccf  jnz     short loc_18004FCD7
0x18004fcd1  mov     [rsp+rax*2+850h+FileName], r15w
0x18004fcd7  add     rax, r12
0x18004fcda  cmp     rax, r10
0x18004fcdd  jb      short loc_18004FCC1
0x18004fcdf  mov     rdx, r10
0x18004fce2  lea     rax, [rsp+850h+FileName]
0x18004fce7  cmp     [rax], r14w
0x18004fceb  jz      short loc_18004FCF5
0x18004fced  add     rax, r8
0x18004fcf0  sub     rdx, r12
0x18004fcf3  jnz     short loc_18004FCE7
0x18004fcf5  mov     rax, rdx
0x18004fcf8  mov     rcx, rdx
0x18004fcfb  neg     rax
0x18004fcfe  sbb     eax, eax
0x18004fd00  sub     r10, rdx
0x18004fd03  not     eax
0x18004fd05  and     eax, 80070057h
0x18004fd0a  neg     rcx
0x18004fd0d  sbb     rbx, rbx
0x18004fd10  and     rbx, r10
0x18004fd13  test    rdx, rdx
0x18004fd16  jz      loc_18004FDC4
0x18004fd1c  mov     edi, 3
0x18004fd21  test    rbx, rbx
0x18004fd24  jz      loc_18004FDEF
0x18004fd2a  cmp     [rsp+rbx*2+850h+var_832], r15w
0x18004fd30  jnz     loc_18004FDEF
0x18004fd36  movzx   eax, [rsp+850h+var_82E]
0x18004fd3b  cmp     rbx, rdi
0x18004fd3e  jnz     short loc_18004FD52
0x18004fd40  cmp     ax, 3Ah ; ':'
0x18004fd44  jnz     short loc_18004FD69
0x18004fd46  cmp     [rsp+850h+var_82C], r15w
0x18004fd4c  jz      loc_18004FDF9
0x18004fd52  cmp     rbx, r8
0x18004fd55  jnz     short loc_18004FD69
0x18004fd57  cmp     [rsp+850h+FileName], r15w
0x18004fd5d  jnz     short loc_18004FD69
0x18004fd5f  cmp     ax, r15w
0x18004fd63  jz      loc_18004FE07
0x18004fd69  dec     rbx
0x18004fd6c  lea     rcx, [rbx+rbx]
0x18004fd70  cmp     rcx, rsi
0x18004fd73  jnb     loc_18004FEED
0x18004fd79  mov     [rsp+rcx+850h+FileName], r14w
0x18004fd7f  test    rbx, rbx
0x18004fd82  jnz     short loc_18004FD2A
0x18004fd84  cmp     [rsp+850h+FileName], r14w
0x18004fd8a  jz      short loc_18004FDA0
0x18004fd8c  lea     rcx, [rsp+850h+FileName]; lpFileName
0x18004fd91  call    cs:__imp_GetFileAttributesW
0x18004fd97  cmp     eax, 0FFFFFFFFh
0x18004fd9a  jz      short loc_18004FDA0
0x18004fd9c  test    al, 10h
0x18004fd9e  jnz     short loc_18004FDC2
0x18004fda0  xor     edx, edx; lpSecurityAttributes
0x18004fda2  lea     rcx, [rsp+850h+FileName]; lpPathName
0x18004fda7  call    cs:__imp_CreateDirectoryW
0x18004fdad  test    eax, eax
0x18004fdaf  jnz     short loc_18004FDC2
0x18004fdb1  call    cs:__imp_GetLastError
0x18004fdb7  cmp     eax, 0B7h
0x18004fdbc  jnz     loc_18004FEBD
0x18004fdc2  xor     eax, eax
0x18004fdc4  mov     rcx, [rbp+750h+var_30]
0x18004fdcb  xor     rcx, rsp; StackCookie
0x18004fdce  call    __security_check_cookie
0x18004fdd3  lea     r11, [rsp+850h+var_20]
0x18004fddb  mov     rbx, [r11+38h]
0x18004fddf  mov     rsi, [r11+40h]
0x18004fde3  mov     rsp, r11
0x18004fde6  pop     r15
0x18004fde8  pop     r14
0x18004fdea  pop     r12
0x18004fdec  pop     rdi
0x18004fded  pop     rbp
0x18004fdee  retn
0x18004fdef  movzx   eax, [rsp+850h+var_82E]
0x18004fdf4  cmp     rbx, r8
0x18004fdf7  jb      short loc_18004FE49
0x18004fdf9  cmp     [rsp+850h+FileName], r15w
0x18004fdff  jnz     short loc_18004FE49
0x18004fe01  cmp     ax, r15w
0x18004fe05  jnz     short loc_18004FE49
0x18004fe07  cmp     rbx, r8
0x18004fe0a  jbe     short loc_18004FE1C
0x18004fe0c  cmp     [rsp+r8*2+850h+FileName], r15w
0x18004fe12  jz      short loc_18004FE1C
0x18004fe14  add     r8, r12
0x18004fe17  cmp     r8, rbx
0x18004fe1a  jb      short loc_18004FE0C
0x18004fe1c  cmp     r8, rbx
0x18004fe1f  lea     rax, [r8+1]
0x18004fe23  cmovnb  rax, r8
0x18004fe27  jmp     short loc_18004FE34
0x18004fe29  cmp     [rsp+rax*2+850h+FileName], r15w
0x18004fe2f  jz      short loc_18004FE39
0x18004fe31  add     rax, r12
0x18004fe34  cmp     rax, rbx
0x18004fe37  jb      short loc_18004FE29
0x18004fe39  cmp     rax, rbx
0x18004fe3c  lea     rdi, [rax+1]
0x18004fe40  cmovnb  rdi, rax
0x18004fe44  jmp     loc_18004FEE3
0x18004fe49  cmp     rbx, rdi
0x18004fe4c  jb      short loc_18004FE60
0x18004fe4e  cmp     ax, 3Ah ; ':'
0x18004fe52  jnz     short loc_18004FE60
0x18004fe54  cmp     [rsp+850h+var_82C], r15w
0x18004fe5a  jz      loc_18004FEE3
0x18004fe60  mov     rdi, r14
0x18004fe63  cmp     rbx, r12
0x18004fe66  jb      short loc_18004FEE3
0x18004fe68  cmp     [rsp+850h+FileName], r15w
0x18004fe6e  cmovz   rdi, r12
0x18004fe72  jmp     short loc_18004FEE3
0x18004fe74  lea     rsi, [rdi+rdi]
0x18004fe78  cmp     [rsp+rsi+850h+FileName], r15w
0x18004fe7e  jnz     short loc_18004FEE0
0x18004fe80  cmp     rsi, 800h
0x18004fe87  jnb     short loc_18004FEED
0x18004fe89  lea     rcx, [rsp+850h+FileName]; lpFileName
0x18004fe8e  mov     [rsp+rsi+850h+FileName], r14w
0x18004fe94  call    cs:__imp_GetFileAttributesW
0x18004fe9a  cmp     eax, 0FFFFFFFFh
0x18004fe9d  jnz     short loc_18004FED2
0x18004fe9f  xor     edx, edx; lpSecurityAttributes
0x18004fea1  lea     rcx, [rsp+850h+FileName]; lpPathName
0x18004fea6  call    cs:__imp_CreateDirectoryW
0x18004feac  test    eax, eax
0x18004feae  jnz     short loc_18004FEDA
0x18004feb0  call    cs:__imp_GetLastError
0x18004feb6  cmp     eax, 0B7h
0x18004febb  jz      short loc_18004FEDA
0x18004febd  test    eax, eax
0x18004febf  jle     loc_18004FDC4
0x18004fec5  movzx   eax, ax
0x18004fec8  or      eax, 80070000h
0x18004fecd  jmp     loc_18004FDC4
0x18004fed2  test    al, 10h
0x18004fed4  jz      loc_18004FC3B
0x18004feda  mov     [rsp+rsi+850h+FileName], r15w
0x18004fee0  add     rdi, r12
0x18004fee3  cmp     rdi, rbx
0x18004fee6  jb      short loc_18004FE74
0x18004fee8  jmp     loc_18004FD84
0x18004feed  call    __report_rangecheckfailure
```
