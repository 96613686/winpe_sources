# telemetryutil::etl::EnsureDirectoryExists(ushort const *)

- ea: `0x1800100a4`
- end: `0x1800103e3`
- name: `?EnsureDirectoryExists@etl@telemetryutil@@YAJPEBG@Z`
- size: `831`
- prototype: `signed int __fastcall(LPCWSTR lpFileName, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x18000ff50`

## callees

- `0x1800021d8`
- `0x18000bbd0`
- `0x1800100a4`
- `0x180010792`
- `0x1800107c0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180010118`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180010281`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180010384`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180010118`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180010281`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180010384`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180010297`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180010396`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180010297`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180010396`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800102a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800103a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800102a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800103a0`

## pseudocode

```c
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

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl) )
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
0x1800100a4  mov     [rsp-8+arg_8], rbx
0x1800100a9  mov     [rsp-8+arg_10], rsi
0x1800100ae  push    rbp
0x1800100af  push    rdi
0x1800100b0  push    r12
0x1800100b2  push    r14
0x1800100b4  push    r15
0x1800100b6  lea     rbp, [rsp-730h]
0x1800100be  sub     rsp, 830h
0x1800100c5  mov     rax, cs:__security_cookie
0x1800100cc  xor     rax, rsp
0x1800100cf  mov     [rbp+750h+var_30], rax
0x1800100d6  mov     rbx, rcx
0x1800100d9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl(void)'::`2'::impl
0x1800100e0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(void)
0x1800100e5  xor     r14d, r14d
0x1800100e8  test    al, al
0x1800100ea  jnz     short loc_1800100F6
0x1800100ec  mov     eax, 80070032h
0x1800100f1  jmp     loc_1800102B4
0x1800100f6  test    rbx, rbx
0x1800100f9  jnz     short loc_180010105
0x1800100fb  mov     eax, 80004003h
0x180010100  jmp     loc_1800102B4
0x180010105  cmp     [rbx], r14w
0x180010109  jnz     short loc_180010115
0x18001010b  mov     eax, 80070057h
0x180010110  jmp     loc_1800102B4
0x180010115  mov     rcx, rbx; lpFileName
0x180010118  call    cs:__imp_GetFileAttributesW
0x18001011e  cmp     eax, 0FFFFFFFFh
0x180010121  jz      short loc_180010135
0x180010123  test    al, 10h
0x180010125  jnz     loc_1800102B2
0x18001012b  mov     eax, 8007010Bh
0x180010130  jmp     loc_1800102B4
0x180010135  mov     esi, 800h
0x18001013a  lea     rcx, [rsp+850h+FileName]; void *
0x18001013f  mov     r8d, esi; Size
0x180010142  xor     edx, edx; Val
0x180010144  call    memset_0
0x180010149  mov     r8d, 2
0x18001014f  lea     rcx, [rsp+850h+FileName]
0x180010154  mov     r10d, 400h
0x18001015a  mov     eax, 7FFFFFFEh
0x18001015f  mov     r9d, r10d
0x180010162  lea     r12d, [r8-1]
0x180010166  test    rax, rax
0x180010169  jz      short loc_180010184
0x18001016b  movzx   edx, word ptr [rbx]
0x18001016e  test    dx, dx
0x180010171  jz      short loc_180010184
0x180010173  mov     [rcx], dx
0x180010176  add     rbx, r8
0x180010179  add     rcx, r8
0x18001017c  sub     rax, r12
0x18001017f  sub     r9, r12
0x180010182  jnz     short loc_180010166
0x180010184  mov     rax, r9
0x180010187  lea     rdx, [rcx-2]
0x18001018b  neg     rax
0x18001018e  sbb     eax, eax
0x180010190  not     eax
0x180010192  and     eax, 8007007Ah
0x180010197  test    r9, r9
0x18001019a  cmovnz  rdx, rcx
0x18001019e  mov     [rdx], r14w
0x1800101a2  jz      loc_1800102B4
0x1800101a8  mov     rax, r14
0x1800101ab  mov     r15d, 5Ch ; '\'
0x1800101b1  movzx   ecx, [rsp+rax*2+850h+FileName]
0x1800101b6  test    cx, cx
0x1800101b9  jz      short loc_1800101CF
0x1800101bb  cmp     cx, 2Fh ; '/'
0x1800101bf  jnz     short loc_1800101C7
0x1800101c1  mov     [rsp+rax*2+850h+FileName], r15w
0x1800101c7  add     rax, r12
0x1800101ca  cmp     rax, r10
0x1800101cd  jb      short loc_1800101B1
0x1800101cf  mov     rdx, r10
0x1800101d2  lea     rax, [rsp+850h+FileName]
0x1800101d7  cmp     [rax], r14w
0x1800101db  jz      short loc_1800101E5
0x1800101dd  add     rax, r8
0x1800101e0  sub     rdx, r12
0x1800101e3  jnz     short loc_1800101D7
0x1800101e5  mov     rax, rdx
0x1800101e8  mov     rcx, rdx
0x1800101eb  neg     rax
0x1800101ee  sbb     eax, eax
0x1800101f0  sub     r10, rdx
0x1800101f3  not     eax
0x1800101f5  and     eax, 80070057h
0x1800101fa  neg     rcx
0x1800101fd  sbb     rbx, rbx
0x180010200  and     rbx, r10
0x180010203  test    rdx, rdx
0x180010206  jz      loc_1800102B4
0x18001020c  mov     edi, 3
0x180010211  test    rbx, rbx
0x180010214  jz      loc_1800102DF
0x18001021a  cmp     [rsp+rbx*2+850h+var_832], r15w
0x180010220  jnz     loc_1800102DF
0x180010226  movzx   eax, [rsp+850h+var_82E]
0x18001022b  cmp     rbx, rdi
0x18001022e  jnz     short loc_180010242
0x180010230  cmp     ax, 3Ah ; ':'
0x180010234  jnz     short loc_180010259
0x180010236  cmp     [rsp+850h+var_82C], r15w
0x18001023c  jz      loc_1800102E9
0x180010242  cmp     rbx, r8
0x180010245  jnz     short loc_180010259
0x180010247  cmp     [rsp+850h+FileName], r15w
0x18001024d  jnz     short loc_180010259
0x18001024f  cmp     ax, r15w
0x180010253  jz      loc_1800102F7
0x180010259  dec     rbx
0x18001025c  lea     rcx, [rbx+rbx]
0x180010260  cmp     rcx, rsi
0x180010263  jnb     loc_1800103DD
0x180010269  mov     [rsp+rcx+850h+FileName], r14w
0x18001026f  test    rbx, rbx
0x180010272  jnz     short loc_18001021A
0x180010274  cmp     [rsp+850h+FileName], r14w
0x18001027a  jz      short loc_180010290
0x18001027c  lea     rcx, [rsp+850h+FileName]; lpFileName
0x180010281  call    cs:__imp_GetFileAttributesW
0x180010287  cmp     eax, 0FFFFFFFFh
0x18001028a  jz      short loc_180010290
0x18001028c  test    al, 10h
0x18001028e  jnz     short loc_1800102B2
0x180010290  xor     edx, edx; lpSecurityAttributes
0x180010292  lea     rcx, [rsp+850h+FileName]; lpPathName
0x180010297  call    cs:__imp_CreateDirectoryW
0x18001029d  test    eax, eax
0x18001029f  jnz     short loc_1800102B2
0x1800102a1  call    cs:__imp_GetLastError
0x1800102a7  cmp     eax, 0B7h
0x1800102ac  jnz     loc_1800103AD
0x1800102b2  xor     eax, eax
0x1800102b4  mov     rcx, [rbp+750h+var_30]
0x1800102bb  xor     rcx, rsp; StackCookie
0x1800102be  call    __security_check_cookie
0x1800102c3  lea     r11, [rsp+850h+var_20]
0x1800102cb  mov     rbx, [r11+38h]
0x1800102cf  mov     rsi, [r11+40h]
0x1800102d3  mov     rsp, r11
0x1800102d6  pop     r15
0x1800102d8  pop     r14
0x1800102da  pop     r12
0x1800102dc  pop     rdi
0x1800102dd  pop     rbp
0x1800102de  retn
0x1800102df  movzx   eax, [rsp+850h+var_82E]
0x1800102e4  cmp     rbx, r8
0x1800102e7  jb      short loc_180010339
0x1800102e9  cmp     [rsp+850h+FileName], r15w
0x1800102ef  jnz     short loc_180010339
0x1800102f1  cmp     ax, r15w
0x1800102f5  jnz     short loc_180010339
0x1800102f7  cmp     rbx, r8
0x1800102fa  jbe     short loc_18001030C
0x1800102fc  cmp     [rsp+r8*2+850h+FileName], r15w
0x180010302  jz      short loc_18001030C
0x180010304  add     r8, r12
0x180010307  cmp     r8, rbx
0x18001030a  jb      short loc_1800102FC
0x18001030c  cmp     r8, rbx
0x18001030f  lea     rax, [r8+1]
0x180010313  cmovnb  rax, r8
0x180010317  jmp     short loc_180010324
0x180010319  cmp     [rsp+rax*2+850h+FileName], r15w
0x18001031f  jz      short loc_180010329
0x180010321  add     rax, r12
0x180010324  cmp     rax, rbx
0x180010327  jb      short loc_180010319
0x180010329  cmp     rax, rbx
0x18001032c  lea     rdi, [rax+1]
0x180010330  cmovnb  rdi, rax
0x180010334  jmp     loc_1800103D3
0x180010339  cmp     rbx, rdi
0x18001033c  jb      short loc_180010350
0x18001033e  cmp     ax, 3Ah ; ':'
0x180010342  jnz     short loc_180010350
0x180010344  cmp     [rsp+850h+var_82C], r15w
0x18001034a  jz      loc_1800103D3
0x180010350  mov     rdi, r14
0x180010353  cmp     rbx, r12
0x180010356  jb      short loc_1800103D3
0x180010358  cmp     [rsp+850h+FileName], r15w
0x18001035e  cmovz   rdi, r12
0x180010362  jmp     short loc_1800103D3
0x180010364  lea     rsi, [rdi+rdi]
0x180010368  cmp     [rsp+rsi+850h+FileName], r15w
0x18001036e  jnz     short loc_1800103D0
0x180010370  cmp     rsi, 800h
0x180010377  jnb     short loc_1800103DD
0x180010379  lea     rcx, [rsp+850h+FileName]; lpFileName
0x18001037e  mov     [rsp+rsi+850h+FileName], r14w
0x180010384  call    cs:__imp_GetFileAttributesW
0x18001038a  cmp     eax, 0FFFFFFFFh
0x18001038d  jnz     short loc_1800103C2
0x18001038f  xor     edx, edx; lpSecurityAttributes
0x180010391  lea     rcx, [rsp+850h+FileName]; lpPathName
0x180010396  call    cs:__imp_CreateDirectoryW
0x18001039c  test    eax, eax
0x18001039e  jnz     short loc_1800103CA
0x1800103a0  call    cs:__imp_GetLastError
0x1800103a6  cmp     eax, 0B7h
0x1800103ab  jz      short loc_1800103CA
0x1800103ad  test    eax, eax
0x1800103af  jle     loc_1800102B4
0x1800103b5  movzx   eax, ax
0x1800103b8  or      eax, 80070000h
0x1800103bd  jmp     loc_1800102B4
0x1800103c2  test    al, 10h
0x1800103c4  jz      loc_18001012B
0x1800103ca  mov     [rsp+rsi+850h+FileName], r15w
0x1800103d0  add     rdi, r12
0x1800103d3  cmp     rdi, rbx
0x1800103d6  jb      short loc_180010364
0x1800103d8  jmp     loc_180010274
0x1800103dd  call    __report_rangecheckfailure
```
