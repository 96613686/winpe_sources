# ConvertDevicePathToDrivePath(ushort const *,ushort *)

- ea: `0x180055060`
- end: `0x1800552b7`
- name: `?ConvertDevicePathToDrivePath@@YAJPEBGPEAG@Z`
- size: `599`
- prototype: `__int64 __fastcall(wchar_t *String1, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180042ddc`

## callees

- `0x180004ea0`
- `0x18000589c`
- `0x180005914`
- `0x18000d62c`
- `0x180054934`
- `0x180055060`
- `0x1800552c0`
- `0x1800554fc`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x18005512a`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x18005512a`
- `api-ms-win-core-file-l1-1-0!GetLogicalDriveStringsW` at `0x1800550e8`
- `api-ms-win-core-file-l1-1-0!GetLogicalDriveStringsW` at `0x1800550e8`

## string_xrefs

- `0x18005525d`: `Bad length for resulting drive path: %d`
- `0x1800551f4`: `Failed to put drive path together [%#x]`

## pseudocode

```c
__int64 __fastcall ConvertDevicePathToDrivePath(wchar_t *String1, unsigned __int16 *a2)
{
  unsigned __int64 v4; // rax
  WCHAR v5; // ax
  WCHAR *v6; // r14
  int v7; // esi
  size_t v8; // rbx
  __int64 v9; // rcx
  __int64 v10; // rax
  unsigned __int64 v11; // rbx
  int v12; // ebx
  __int64 v14; // rdx
  __int64 v15; // r8
  WCHAR DeviceName; // [rsp+30h] [rbp-D0h] BYREF
  int v18; // [rsp+32h] [rbp-CEh]
  WCHAR Buffer[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR TargetPath[264]; // [rsp+250h] [rbp+150h] BYREF

  memset_0(Buffer, 0, 0x208u);
  if ( !String1 )
    return 2147942487LL;
  if ( !a2 )
    return 2147942487LL;
  v4 = -1;
  do
    ++v4;
  while ( String1[v4] );
  if ( v4 > 0x104 )
    return 2147942487LL;
  *a2 = 0;
  if ( !GetLogicalDriveStringsW(0x103u, Buffer) )
    return 2147500037LL;
  v5 = Buffer[0];
  v6 = Buffer;
  v7 = 0;
  v18 = 58;
  TargetPath[0] = 0;
  while ( 1 )
  {
    DeviceName = v5;
    if ( !QueryDosDeviceW(&DeviceName, TargetPath, 0x103u) )
      goto LABEL_23;
    v8 = -1;
    do
      ++v8;
    while ( TargetPath[v8] );
    if ( v8 >= 0x104 )
      goto LABEL_23;
    if ( wcsnicmp(String1, TargetPath, v8) )
    {
      v7 = 0;
      goto LABEL_23;
    }
    String1 += v8;
    v9 = -1;
    do
      ++v9;
    while ( *(&DeviceName + v9) );
    v10 = -1;
    do
      ++v10;
    while ( String1[v10] );
    v11 = v9 + v10 + 1;
    if ( v11 >= 0x104 )
      break;
    v7 = 1;
    v12 = StringCchPrintfW(a2, 0x104u, L"%s%s", &DeviceName, String1);
    if ( v12 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        Log("Failed to put drive path together [%#x]", v12);
        WPP_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          WPP_affb35cab6d5398f26b14394a7a3d400_Traceguids,
          (unsigned int)v12);
      }
      return 2147500037LL;
    }
LABEL_23:
    while ( *v6++ )
      ;
    if ( v7 )
      return 0;
    v5 = *v6;
    if ( !*v6 )
      return 2147500037LL;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    Log("Bad length for resulting drive path: %d", v11);
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, v15, (unsigned int)v11);
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x180055060  mov     [rsp-8+arg_10], rbx
0x180055065  push    rbp
0x180055066  push    rsi
0x180055067  push    rdi
0x180055068  push    r12
0x18005506a  push    r13
0x18005506c  push    r14
0x18005506e  push    r15
0x180055070  lea     rbp, [rsp-370h]
0x180055078  sub     rsp, 470h
0x18005507f  mov     rax, cs:__security_cookie
0x180055086  xor     rax, rsp
0x180055089  mov     [rbp+3A0h+var_40], rax
0x180055090  mov     r15, rdx
0x180055093  mov     rdi, rcx
0x180055096  xor     edx, edx; Val
0x180055098  lea     rcx, [rsp+4A0h+Buffer]; void *
0x18005509d  mov     r8d, 208h; Size
0x1800550a3  call    memset_0
0x1800550a8  xor     r12d, r12d
0x1800550ab  test    rdi, rdi
0x1800550ae  jz      loc_180055288
0x1800550b4  test    r15, r15
0x1800550b7  jz      loc_180055288
0x1800550bd  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800550c1  mov     rax, r13
0x1800550c4  inc     rax
0x1800550c7  cmp     [rdi+rax*2], r12w
0x1800550cc  jnz     short loc_1800550C4
0x1800550ce  cmp     rax, 104h
0x1800550d4  ja      loc_180055288
0x1800550da  lea     rdx, [rsp+4A0h+Buffer]; lpBuffer
0x1800550df  mov     [r15], r12w
0x1800550e3  mov     ecx, 103h; nBufferLength
0x1800550e8  call    cs:__imp_GetLogicalDriveStringsW
0x1800550ee  test    eax, eax
0x1800550f0  jz      loc_18005527C
0x1800550f6  movzx   eax, [rsp+4A0h+Buffer]
0x1800550fb  lea     r14, [rsp+4A0h+Buffer]
0x180055100  mov     esi, r12d
0x180055103  mov     [rsp+4A0h+var_46E], 3Ah ; ':'
0x18005510b  mov     [rbp+3A0h+TargetPath], r12w
0x180055113  mov     r8d, 103h; ucchMax
0x180055119  mov     [rsp+4A0h+DeviceName], ax
0x18005511e  lea     rdx, [rbp+3A0h+TargetPath]; lpTargetPath
0x180055125  lea     rcx, [rsp+4A0h+DeviceName]; lpDeviceName
0x18005512a  call    cs:__imp_QueryDosDeviceW
0x180055130  test    eax, eax
0x180055132  jz      loc_180055222
0x180055138  lea     rax, [rbp+3A0h+TargetPath]
0x18005513f  mov     rbx, r13
0x180055142  inc     rbx
0x180055145  cmp     [rax+rbx*2], r12w
0x18005514a  jnz     short loc_180055142
0x18005514c  cmp     rbx, 104h
0x180055153  jnb     loc_180055222
0x180055159  mov     r8, rbx; MaxCount
0x18005515c  lea     rdx, [rbp+3A0h+TargetPath]; String2
0x180055163  mov     rcx, rdi; String1
0x180055166  call    _wcsnicmp
0x18005516b  test    eax, eax
0x18005516d  jnz     loc_18005521F
0x180055173  lea     rdi, [rdi+rbx*2]
0x180055177  mov     rcx, r13
0x18005517a  lea     rax, [rsp+4A0h+DeviceName]
0x18005517f  inc     rcx
0x180055182  cmp     [rax+rcx*2], r12w
0x180055187  jnz     short loc_18005517F
0x180055189  mov     rax, r13
0x18005518c  inc     rax
0x18005518f  cmp     [rdi+rax*2], r12w
0x180055194  jnz     short loc_18005518C
0x180055196  lea     rbx, [rax+1]
0x18005519a  mov     eax, 104h
0x18005519f  add     rbx, rcx
0x1800551a2  cmp     rbx, rax
0x1800551a5  jnb     loc_180055242
0x1800551ab  lea     r9, [rsp+4A0h+DeviceName]
0x1800551b0  mov     [rsp+4A0h+var_480], rdi
0x1800551b5  lea     r8, aSS_2; "%s%s"
0x1800551bc  mov     edx, eax; unsigned __int64
0x1800551be  mov     rcx, r15; unsigned __int16 *
0x1800551c1  mov     esi, 1
0x1800551c6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800551cb  mov     ebx, eax
0x1800551cd  test    eax, eax
0x1800551cf  jns     short loc_180055222
0x1800551d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800551d8  lea     rax, WPP_GLOBAL_Control
0x1800551df  cmp     rcx, rax
0x1800551e2  jz      loc_18005527C
0x1800551e8  test    [rcx+1Ch], sil
0x1800551ec  jz      loc_18005527C
0x1800551f2  mov     edx, ebx
0x1800551f4  lea     rcx, aFailedToPutDri; "Failed to put drive path together [%#x]"
0x1800551fb  call    ?Log@@YAXPEBDZZ; Log(char const *,...)
0x180055200  mov     rcx, cs:WPP_GLOBAL_Control
0x180055207  lea     edx, [rsi+0Ah]
0x18005520a  mov     r9d, ebx
0x18005520d  lea     r8, WPP_affb35cab6d5398f26b14394a7a3d400_Traceguids
0x180055214  mov     rcx, [rcx+10h]
0x180055218  call    WPP_SF_D
0x18005521d  jmp     short loc_18005527C
0x18005521f  mov     esi, r12d
0x180055222  movzx   eax, word ptr [r14]
0x180055226  add     r14, 2
0x18005522a  test    ax, ax
0x18005522d  jnz     short loc_180055222
0x18005522f  test    esi, esi
0x180055231  jnz     short loc_180055283
0x180055233  movzx   eax, word ptr [r14]
0x180055237  test    ax, ax
0x18005523a  jnz     loc_180055113
0x180055240  jmp     short loc_18005527C
0x180055242  mov     rcx, cs:WPP_GLOBAL_Control
0x180055249  lea     rax, WPP_GLOBAL_Control
0x180055250  cmp     rcx, rax
0x180055253  jz      short loc_18005527C
0x180055255  test    byte ptr [rcx+1Ch], 1
0x180055259  jz      short loc_18005527C
0x18005525b  mov     edx, ebx
0x18005525d  lea     rcx, aBadLengthForRe; "Bad length for resulting drive path: %d"
0x180055264  call    ?Log@@YAXPEBDZZ; Log(char const *,...)
0x180055269  mov     rcx, cs:WPP_GLOBAL_Control
0x180055270  mov     r9d, ebx
0x180055273  mov     rcx, [rcx+10h]
0x180055277  call    WPP_SF_d
0x18005527c  mov     eax, 80004005h
0x180055281  jmp     short loc_18005528D
0x180055283  mov     eax, r12d
0x180055286  jmp     short loc_18005528D
0x180055288  mov     eax, 80070057h
0x18005528d  mov     rcx, [rbp+3A0h+var_40]
0x180055294  xor     rcx, rsp; StackCookie
0x180055297  call    __security_check_cookie
0x18005529c  mov     rbx, [rsp+4A0h+arg_10]
0x1800552a4  add     rsp, 470h
0x1800552ab  pop     r15
0x1800552ad  pop     r14
0x1800552af  pop     r13
0x1800552b1  pop     r12
0x1800552b3  pop     rdi
0x1800552b4  pop     rsi
0x1800552b5  pop     rbp
0x1800552b6  retn
```
