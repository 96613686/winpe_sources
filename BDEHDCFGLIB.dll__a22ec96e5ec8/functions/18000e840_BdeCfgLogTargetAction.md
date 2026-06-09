# BdeCfgLogTargetAction

- ea: `0x18000e840`
- end: `0x18000eb35`
- name: `BdeCfgLogTargetAction`
- size: `757`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180010800`

## callees

- `0x18000e840`
- `0x1800135c0`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x18000eaf5`
- `ADVAPI32!EventWrite` at `0x18000eaf5`

## pseudocode

```c
__int64 __fastcall BdeCfgLogTargetAction(__int64 a1)
{
  int v2; // ebx
  int v3; // ecx
  int v4; // ecx
  ULONG v5; // edx
  __int64 v6; // rcx
  const EVENT_DESCRIPTOR *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rax
  signed int v13; // eax
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+30h] [rbp-88h] BYREF
  int *v16; // [rsp+40h] [rbp-78h]
  __int64 v17; // [rsp+48h] [rbp-70h]
  int *v18; // [rsp+50h] [rbp-68h]
  __int64 v19; // [rsp+58h] [rbp-60h]
  __int64 v20; // [rsp+60h] [rbp-58h]
  __int64 v21; // [rsp+68h] [rbp-50h]
  __int64 v22; // [rsp+70h] [rbp-48h]
  __int64 v23; // [rsp+78h] [rbp-40h]
  int *v24; // [rsp+80h] [rbp-38h]
  int v25; // [rsp+88h] [rbp-30h]
  int v26; // [rsp+8Ch] [rbp-2Ch]
  int v27; // [rsp+90h] [rbp-28h] BYREF
  wchar_t v28; // [rsp+94h] [rbp-24h]
  int v29; // [rsp+98h] [rbp-20h] BYREF
  wchar_t v30; // [rsp+9Ch] [rbp-1Ch]

  v27 = *(_DWORD *)L" :";
  v28 = asc_18001763C[2];
  v29 = *(_DWORD *)L" :";
  v30 = asc_18001763C[2];
  v2 = 0;
  if ( !g_EventRegistrationHandle )
    v2 = -1063256042;
  if ( v2 >= 0 )
  {
    if ( a1 )
    {
      v3 = *(_DWORD *)a1 - 1;
      if ( v3 )
      {
        v4 = v3 - 1;
        if ( v4 )
        {
          if ( v4 != 1 )
            return (unsigned int)-1063256037;
          UserData.Ptr = a1 + 528;
          *(_QWORD *)&UserData.Size = 8;
          v16 = (int *)(a1 + 536);
          v17 = 8;
          LOWORD(v29) = *(_WORD *)(a1 + 544);
          v5 = 3;
          v6 = -1;
          do
            ++v6;
          while ( *((_WORD *)&v29 + v6) );
          v18 = &v29;
          v19 = (unsigned int)(2 * v6 + 2);
          v7 = &BDECFG_EVT_LOG_UNALLOCATED_ACTION;
        }
        else
        {
          v8 = -1;
          v9 = -1;
          do
            ++v9;
          while ( *(_WORD *)(a1 + 536 + 2 * v9) );
          UserData.Ptr = a1 + 536;
          UserData.Size = 2 * v9 + 2;
          UserData.Reserved = 0;
          LOWORD(v27) = *(_WORD *)(a1 + 1084);
          do
            ++v8;
          while ( *((_WORD *)&v27 + v8) );
          v16 = &v27;
          v17 = (unsigned int)(2 * v8 + 2);
          v18 = (int *)(a1 + 1088);
          v5 = 4;
          v19 = 4;
          v20 = a1 + 1092;
          v21 = 4;
          v7 = (const EVENT_DESCRIPTOR *)BDECFG_EVT_LOG_MERGE_ACTION;
        }
      }
      else
      {
        v10 = -1;
        v11 = -1;
        do
          ++v11;
        while ( *(_WORD *)(a1 + 536 + 2 * v11) );
        UserData.Ptr = a1 + 536;
        UserData.Size = 2 * v11 + 2;
        UserData.Reserved = 0;
        LOWORD(v27) = *(_WORD *)(a1 + 1084);
        v12 = -1;
        do
          ++v12;
        while ( *((_WORD *)&v27 + v12) );
        v16 = &v27;
        v17 = (unsigned int)(2 * v12 + 2);
        v18 = (int *)(a1 + 1088);
        v19 = 4;
        v20 = a1 + 1092;
        v21 = 4;
        v22 = a1 + 1096;
        v23 = 8;
        LOWORD(v29) = *(_WORD *)(a1 + 1104);
        v5 = 6;
        do
          ++v10;
        while ( *((_WORD *)&v29 + v10) );
        v24 = &v29;
        v25 = 2 * v10 + 2;
        v26 = 0;
        v7 = (const EVENT_DESCRIPTOR *)BDECFG_EVT_LOG_SHRINK_ACTION;
      }
      v13 = EventWrite(g_EventRegistrationHandle, v7, v5, &UserData);
      if ( v13 )
      {
        if ( v13 > 0 )
          return (unsigned __int16)v13 | 0x80070000;
        else
          return (unsigned int)v13;
      }
    }
    else
    {
      return (unsigned int)-2147024809;
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000e840  mov     r11, rsp
0x18000e843  mov     [r11+8], rbx
0x18000e847  push    rdi
0x18000e848  sub     rsp, 0B0h
0x18000e84f  mov     rax, cs:__security_cookie
0x18000e856  xor     rax, rsp
0x18000e859  mov     [rsp+0B8h+var_18], rax
0x18000e861  mov     r8, rcx
0x18000e864  mov     edx, dword ptr cs:asc_18001763C; " :"
0x18000e86a  mov     [r11-28h], edx
0x18000e86e  movzx   eax, word ptr cs:asc_18001763C+4; ""
0x18000e875  mov     [r11-24h], ax
0x18000e87a  mov     [r11-20h], edx
0x18000e87e  mov     [r11-1Ch], ax
0x18000e883  xor     edi, edi
0x18000e885  mov     ebx, edi
0x18000e887  mov     eax, 0C0A00016h
0x18000e88c  mov     r10, cs:?g_EventRegistrationHandle@@3_KA; unsigned __int64 g_EventRegistrationHandle
0x18000e893  test    r10, r10
0x18000e896  cmovz   ebx, eax
0x18000e899  mov     [rsp+0B8h+var_98], ebx
0x18000e89d  test    ebx, ebx
0x18000e89f  js      loc_18000EB12
0x18000e8a5  test    rcx, rcx
0x18000e8a8  jnz     short loc_18000E8B4
0x18000e8aa  mov     ebx, 80070057h
0x18000e8af  jmp     loc_18000EB0E
0x18000e8b4  mov     ecx, [rcx]
0x18000e8b6  sub     ecx, 1
0x18000e8b9  jz      loc_18000E9EB
0x18000e8bf  sub     ecx, 1
0x18000e8c2  jz      loc_18000E950
0x18000e8c8  cmp     ecx, 1
0x18000e8cb  jz      short loc_18000E8D7
0x18000e8cd  mov     ebx, 0C0A0001Bh
0x18000e8d2  jmp     loc_18000EB0E
0x18000e8d7  lea     rax, [r8+210h]
0x18000e8de  mov     [rsp+0B8h+UserData.Ptr], rax
0x18000e8e3  mov     qword ptr [rsp+0B8h+UserData.Size], 8
0x18000e8ec  add     rax, 8
0x18000e8f0  mov     [rsp+0B8h+var_78], rax
0x18000e8f5  mov     [rsp+0B8h+var_70], 8
0x18000e8fe  movzx   eax, word ptr [r8+220h]
0x18000e906  mov     [rsp+0B8h+var_20], ax
0x18000e90e  mov     edx, 3
0x18000e913  lea     rax, [rsp+0B8h+var_20]
0x18000e91b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000e91f  inc     rcx
0x18000e922  cmp     [rax+rcx*2], di
0x18000e926  jnz     short loc_18000E91F
0x18000e928  lea     rax, [rsp+0B8h+var_20]
0x18000e930  mov     [rsp+0B8h+var_68], rax
0x18000e935  lea     eax, ds:2[rcx*2]
0x18000e93c  mov     dword ptr [rsp+0B8h+var_60], eax
0x18000e940  mov     dword ptr [rsp+0B8h+var_60+4], edi
0x18000e944  lea     rax, BDECFG_EVT_LOG_UNALLOCATED_ACTION
0x18000e94b  jmp     loc_18000EAE7
0x18000e950  lea     rdx, [r8+218h]
0x18000e957  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000e95b  mov     rax, rcx
0x18000e95e  inc     rax
0x18000e961  cmp     [rdx+rax*2], di
0x18000e965  jnz     short loc_18000E95E
0x18000e967  mov     [rsp+0B8h+UserData.Ptr], rdx
0x18000e96c  lea     eax, ds:2[rax*2]
0x18000e973  mov     [rsp+0B8h+UserData.Size], eax
0x18000e977  mov     dword ptr [rsp+0B8h+UserData.0Ch], edi
0x18000e97b  movzx   eax, word ptr [r8+43Ch]
0x18000e983  mov     [rsp+0B8h+var_28], ax
0x18000e98b  lea     rax, [rsp+0B8h+var_28]
0x18000e993  inc     rcx
0x18000e996  cmp     [rax+rcx*2], di
0x18000e99a  jnz     short loc_18000E993
0x18000e99c  lea     rax, [rsp+0B8h+var_28]
0x18000e9a4  mov     [rsp+0B8h+var_78], rax
0x18000e9a9  lea     eax, ds:2[rcx*2]
0x18000e9b0  mov     dword ptr [rsp+0B8h+var_70], eax
0x18000e9b4  mov     dword ptr [rsp+0B8h+var_70+4], edi
0x18000e9b8  lea     rax, [r8+440h]
0x18000e9bf  mov     [rsp+0B8h+var_68], rax
0x18000e9c4  mov     edx, 4
0x18000e9c9  mov     [rsp+0B8h+var_60], rdx
0x18000e9ce  lea     rax, [r8+444h]
0x18000e9d5  mov     [rsp+0B8h+var_58], rax
0x18000e9da  mov     [rsp+0B8h+var_50], rdx
0x18000e9df  lea     rax, BDECFG_EVT_LOG_MERGE_ACTION
0x18000e9e6  jmp     loc_18000EAE7
0x18000e9eb  lea     rdx, [r8+218h]
0x18000e9f2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000e9f6  mov     rax, rcx
0x18000e9f9  inc     rax
0x18000e9fc  cmp     [rdx+rax*2], di
0x18000ea00  jnz     short loc_18000E9F9
0x18000ea02  mov     [rsp+0B8h+UserData.Ptr], rdx
0x18000ea07  lea     eax, ds:2[rax*2]
0x18000ea0e  mov     [rsp+0B8h+UserData.Size], eax
0x18000ea12  mov     dword ptr [rsp+0B8h+UserData.0Ch], edi
0x18000ea16  movzx   eax, word ptr [r8+43Ch]
0x18000ea1e  mov     [rsp+0B8h+var_28], ax
0x18000ea26  lea     rdx, [rsp+0B8h+var_28]
0x18000ea2e  mov     rax, rcx
0x18000ea31  inc     rax
0x18000ea34  cmp     [rdx+rax*2], di
0x18000ea38  jnz     short loc_18000EA31
0x18000ea3a  lea     rdx, [rsp+0B8h+var_28]
0x18000ea42  mov     [rsp+0B8h+var_78], rdx
0x18000ea47  lea     eax, ds:2[rax*2]
0x18000ea4e  mov     dword ptr [rsp+0B8h+var_70], eax
0x18000ea52  mov     dword ptr [rsp+0B8h+var_70+4], edi
0x18000ea56  lea     rax, [r8+440h]
0x18000ea5d  mov     [rsp+0B8h+var_68], rax
0x18000ea62  mov     [rsp+0B8h+var_60], 4
0x18000ea6b  lea     rax, [r8+444h]
0x18000ea72  mov     [rsp+0B8h+var_58], rax
0x18000ea77  mov     [rsp+0B8h+var_50], 4
0x18000ea80  lea     rax, [r8+448h]
0x18000ea87  mov     [rsp+0B8h+var_48], rax
0x18000ea8c  mov     [rsp+0B8h+var_40], 8
0x18000ea95  movzx   eax, word ptr [r8+450h]
0x18000ea9d  mov     [rsp+0B8h+var_20], ax
0x18000eaa5  mov     edx, 6
0x18000eaaa  lea     rax, [rsp+0B8h+var_20]
0x18000eab2  inc     rcx
0x18000eab5  cmp     [rax+rcx*2], di
0x18000eab9  jnz     short loc_18000EAB2
0x18000eabb  lea     rax, [rsp+0B8h+var_20]
0x18000eac3  mov     [rsp+0B8h+var_38], rax
0x18000eacb  lea     eax, ds:2[rcx*2]
0x18000ead2  mov     [rsp+0B8h+var_30], eax
0x18000ead9  mov     [rsp+0B8h+var_2C], edi
0x18000eae0  lea     rax, BDECFG_EVT_LOG_SHRINK_ACTION
0x18000eae7  lea     r9, [rsp+0B8h+UserData]; UserData
0x18000eaec  mov     r8d, edx; UserDataCount
0x18000eaef  mov     rdx, rax; EventDescriptor
0x18000eaf2  mov     rcx, r10; RegHandle
0x18000eaf5  call    cs:__imp_EventWrite
0x18000eafb  test    eax, eax
0x18000eafd  jz      short loc_18000EB12
0x18000eaff  jg      short loc_18000EB05
0x18000eb01  mov     ebx, eax
0x18000eb03  jmp     short loc_18000EB0E
0x18000eb05  movzx   ebx, ax
0x18000eb08  or      ebx, 80070000h
0x18000eb0e  mov     [rsp+0B8h+var_98], ebx
0x18000eb12  mov     eax, ebx
0x18000eb14  mov     rcx, [rsp+0B8h+var_18]
0x18000eb1c  xor     rcx, rsp; StackCookie
0x18000eb1f  call    __security_check_cookie
0x18000eb24  mov     rbx, [rsp+0B8h+arg_0]
0x18000eb2c  add     rsp, 0B0h
0x18000eb33  pop     rdi
0x18000eb34  retn
0x180014149  push    rbp
0x18001414b  sub     rsp, 20h
0x18001414f  mov     rbp, rdx
0x180014152  add     rsp, 20h
0x180014156  pop     rbp
0x180014157  retn
```
