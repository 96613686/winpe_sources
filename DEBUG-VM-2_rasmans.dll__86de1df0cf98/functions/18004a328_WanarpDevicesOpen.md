# WanarpDevicesOpen

- ea: `0x18004a328`
- end: `0x18004a533`
- name: `WanarpDevicesOpen`
- size: `523`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18002cd40`
- `0x18004a1a8`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x18004a328`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a415`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a4a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a415`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a4a7`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18004a402`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18004a494`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18004a402`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18004a494`

## pseudocode

```c
__int64 __fastcall WanarpDevicesOpen(_QWORD *a1, _QWORD *a2)
{
  struct _LIST_ENTRY *v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // r9
  bool v8; // zf
  DWORD LastError; // eax

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 633, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  v5 = 0;
  if ( a1 )
  {
    v8 = (char *)g_hWanarp + 1 == 0;
    *a1 = -1;
    if ( v8 )
    {
      g_hWanarp = CreateFileA("\\\\.\\WANARP", 0xC0000000, 3u, 0, 3u, 0x40000000u, 0);
      if ( g_hWanarp == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError )
        {
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
            return v5;
          if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            goto LABEL_34;
          v6 = 635;
LABEL_19:
          v7 = LastError;
          goto LABEL_11;
        }
      }
    }
    if ( !a2 )
      goto LABEL_28;
    goto LABEL_21;
  }
  if ( a2 )
  {
LABEL_21:
    v8 = (char *)g_hWanarpv6 + 1 == 0;
    *a2 = -1;
    if ( v8 )
    {
      g_hWanarpv6 = CreateFileA("\\\\.\\WANARPV6", 0xC0000000, 3u, 0, 3u, 0x40000000u, 0);
      if ( g_hWanarpv6 == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError )
        {
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
            return v5;
          if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            goto LABEL_34;
          v6 = 636;
          goto LABEL_19;
        }
LABEL_29:
        if ( a1 )
          *a1 = g_hWanarp;
        if ( a2 )
          *a2 = g_hWanarpv6;
        goto LABEL_33;
      }
    }
LABEL_28:
    if ( v5 )
      goto LABEL_33;
    goto LABEL_29;
  }
  v5 = 87;
  if ( v4 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    return v5;
  if ( (HIDWORD(v4[1].Blink) & 0x2000) != 0 && BYTE1(v4[1].Blink) >= 2u )
  {
    v6 = 634;
    v7 = 87;
LABEL_11:
    WPP_SF_d(v4[1].Flink, v6, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, v7);
LABEL_33:
    v4 = WPP_GLOBAL_Control;
  }
LABEL_34:
  if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v4[1].Blink) & 0x2000) != 0
    && BYTE1(v4[1].Blink) >= 6u )
  {
    WPP_SF_d(v4[1].Flink, 637, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, v5);
  }
  return v5;
}

```

## disassembly

```asm
0x18004a328  push    rbx
0x18004a32a  push    rsi
0x18004a32b  push    rdi
0x18004a32c  push    r12
0x18004a32e  push    r14
0x18004a330  push    r15
0x18004a332  sub     rsp, 48h
0x18004a336  mov     rdi, rdx
0x18004a339  mov     rsi, rcx
0x18004a33c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a343  lea     r15, WPP_GLOBAL_Control
0x18004a34a  lea     r12, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x18004a351  mov     r14d, 2000h
0x18004a357  cmp     rcx, r15
0x18004a35a  jz      short loc_18004A380
0x18004a35c  test    [rcx+1Ch], r14d
0x18004a360  jz      short loc_18004A380
0x18004a362  cmp     byte ptr [rcx+19h], 6
0x18004a366  jb      short loc_18004A380
0x18004a368  mov     rcx, [rcx+10h]
0x18004a36c  mov     edx, 279h
0x18004a371  mov     r8, r12
0x18004a374  call    WPP_SF_
0x18004a379  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a380  xor     ebx, ebx
0x18004a382  test    rsi, rsi
0x18004a385  jnz     short loc_18004A3C9
0x18004a387  test    rdi, rdi
0x18004a38a  jnz     loc_18004A457
0x18004a390  lea     ebx, [rsi+57h]
0x18004a393  cmp     rcx, r15
0x18004a396  jz      loc_18004A523
0x18004a39c  test    [rcx+1Ch], r14d
0x18004a3a0  jz      loc_18004A4FE
0x18004a3a6  cmp     byte ptr [rcx+19h], 2
0x18004a3aa  jb      loc_18004A4FE
0x18004a3b0  mov     edx, 27Ah
0x18004a3b5  mov     r9d, ebx
0x18004a3b8  mov     rcx, [rcx+10h]
0x18004a3bc  mov     r8, r12
0x18004a3bf  call    WPP_SF_d
0x18004a3c4  jmp     loc_18004A4F7
0x18004a3c9  cmp     cs:g_hWanarp, 0FFFFFFFFFFFFFFFFh
0x18004a3d1  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x18004a3d8  jnz     short loc_18004A452
0x18004a3da  xor     r9d, r9d; lpSecurityAttributes
0x18004a3dd  mov     [rsp+78h+hTemplateFile], rbx; hTemplateFile
0x18004a3e2  mov     [rsp+78h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x18004a3ea  lea     rcx, aWanarp; "\\\\.\\WANARP"
0x18004a3f1  mov     edx, 0C0000000h; dwDesiredAccess
0x18004a3f6  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x18004a3fe  lea     r8d, [r9+3]; dwShareMode
0x18004a402  call    cs:__imp_CreateFileA
0x18004a408  mov     cs:g_hWanarp, rax
0x18004a40f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004a413  jnz     short loc_18004A452
0x18004a415  call    cs:__imp_GetLastError
0x18004a41b  mov     ebx, eax
0x18004a41d  test    eax, eax
0x18004a41f  jz      short loc_18004A452
0x18004a421  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a428  cmp     rcx, r15
0x18004a42b  jz      loc_18004A523
0x18004a431  test    [rcx+1Ch], r14d
0x18004a435  jz      loc_18004A4FE
0x18004a43b  cmp     byte ptr [rcx+19h], 2
0x18004a43f  jb      loc_18004A4FE
0x18004a445  mov     edx, 27Bh
0x18004a44a  mov     r9d, eax
0x18004a44d  jmp     loc_18004A3B8
0x18004a452  test    rdi, rdi
0x18004a455  jz      short loc_18004A4D5
0x18004a457  cmp     cs:g_hWanarpv6, 0FFFFFFFFFFFFFFFFh
0x18004a45f  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x18004a466  jnz     short loc_18004A4D5
0x18004a468  xor     r9d, r9d; lpSecurityAttributes
0x18004a46b  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x18004a474  mov     [rsp+78h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x18004a47c  lea     rcx, aWanarpv6; "\\\\.\\WANARPV6"
0x18004a483  mov     edx, 0C0000000h; dwDesiredAccess
0x18004a488  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x18004a490  lea     r8d, [r9+3]; dwShareMode
0x18004a494  call    cs:__imp_CreateFileA
0x18004a49a  mov     cs:g_hWanarpv6, rax
0x18004a4a1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004a4a5  jnz     short loc_18004A4D5
0x18004a4a7  call    cs:__imp_GetLastError
0x18004a4ad  mov     ebx, eax
0x18004a4af  test    eax, eax
0x18004a4b1  jz      short loc_18004A4D9
0x18004a4b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a4ba  cmp     rcx, r15
0x18004a4bd  jz      short loc_18004A523
0x18004a4bf  test    [rcx+1Ch], r14d
0x18004a4c3  jz      short loc_18004A4FE
0x18004a4c5  cmp     byte ptr [rcx+19h], 2
0x18004a4c9  jb      short loc_18004A4FE
0x18004a4cb  mov     edx, 27Ch
0x18004a4d0  jmp     loc_18004A44A
0x18004a4d5  test    ebx, ebx
0x18004a4d7  jnz     short loc_18004A4F7
0x18004a4d9  test    rsi, rsi
0x18004a4dc  jz      short loc_18004A4E8
0x18004a4de  mov     rax, cs:g_hWanarp
0x18004a4e5  mov     [rsi], rax
0x18004a4e8  test    rdi, rdi
0x18004a4eb  jz      short loc_18004A4F7
0x18004a4ed  mov     rax, cs:g_hWanarpv6
0x18004a4f4  mov     [rdi], rax
0x18004a4f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a4fe  cmp     rcx, r15
0x18004a501  jz      short loc_18004A523
0x18004a503  test    [rcx+1Ch], r14d
0x18004a507  jz      short loc_18004A523
0x18004a509  cmp     byte ptr [rcx+19h], 6
0x18004a50d  jb      short loc_18004A523
0x18004a50f  mov     rcx, [rcx+10h]
0x18004a513  mov     edx, 27Dh
0x18004a518  mov     r9d, ebx
0x18004a51b  mov     r8, r12
0x18004a51e  call    WPP_SF_d
0x18004a523  mov     eax, ebx
0x18004a525  add     rsp, 48h
0x18004a529  pop     r15
0x18004a52b  pop     r14
0x18004a52d  pop     r12
0x18004a52f  pop     rdi
0x18004a530  pop     rsi
0x18004a531  pop     rbx
0x18004a532  retn
```
