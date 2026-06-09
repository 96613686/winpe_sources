# BdeCfgLogError

- ea: `0x18000e300`
- end: `0x18000e50b`
- name: `BdeCfgLogError`
- size: `523`
- prototype: `__int64 __fastcall(int, int)`
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002460`
- `0x180002814`
- `0x180003580`
- `0x180007bd0`
- `0x18000d510`
- `0x18000fb40`
- `0x1800101a0`
- `0x180010800`

## callees

- `0x18000e300`
- `0x1800135c0`

## import_xrefs

- `ntdll!WinSqmAddToStreamEx` at `0x18000e4a4`
- `ntdll!WinSqmAddToStreamEx` at `0x18000e4a4`
- `ADVAPI32!EventWrite` at `0x18000e4bf`
- `ADVAPI32!EventWrite` at `0x18000e4bf`
- `KERNEL32!FormatMessageW` at `0x18000e3b2`
- `KERNEL32!FormatMessageW` at `0x18000e3b2`
- `KERNEL32!LocalFree` at `0x18000e4e6`
- `KERNEL32!LocalFree` at `0x1800142f2`
- `KERNEL32!LocalFree` at `0x18000e4e6`
- `KERNEL32!LocalFree` at `0x1800142f2`

## pseudocode

```c
__int64 __fastcall BdeCfgLogError(int a1, int a2)
{
  DWORD v4; // r8d
  int v5; // esi
  signed int v6; // ebx
  DWORD v7; // ecx
  int v8; // edi
  int v9; // edi
  int v10; // edi
  __int64 *v11; // rdi
  signed int v12; // eax
  int v14; // [rsp+40h] [rbp-88h] BYREF
  int v15; // [rsp+48h] [rbp-80h]
  signed int v16; // [rsp+4Ch] [rbp-7Ch]
  WCHAR Buffer[4]; // [rsp+50h] [rbp-78h] BYREF
  _DWORD v18[8]; // [rsp+58h] [rbp-70h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+78h] [rbp-50h] BYREF
  const OLECHAR *v20; // [rsp+88h] [rbp-40h]
  __int64 v21; // [rsp+90h] [rbp-38h]

  v4 = a2;
  v14 = a2;
  *(_QWORD *)Buffer = 0;
  v5 = 0;
  v6 = 0;
  if ( !g_EventRegistrationHandle )
    v6 = -1063256042;
  v16 = v6;
  if ( v6 >= 0 )
  {
    v15 = 1;
    UserData.Ptr = (ULONGLONG)&v14;
    *(_QWORD *)&UserData.Size = 4;
    if ( (a2 & 0x1FFF0000) == 0x70000 && a2 < 0 )
    {
      v4 = (unsigned __int16)a2;
      v14 = (unsigned __int16)a2;
    }
    v7 = FormatMessageW(0x1BFFu, g_hInstance, v4, 0, Buffer, 0, 0);
    v15 = 2;
    if ( v7 )
    {
      v20 = *(const OLECHAR **)Buffer;
      v21 = 2 * v7 + 2;
    }
    else
    {
      v20 = &word_180017638;
      v21 = 2;
      v6 = 0;
      v16 = 0;
    }
    v8 = a1 - 1;
    if ( v8 )
    {
      v9 = v8 - 1;
      if ( v9 )
      {
        v10 = v9 - 1;
        if ( v10 )
        {
          if ( v10 != 1 )
          {
            v11 = (__int64 *)&BDECFG_EVT_TOOL_ERROR;
            goto LABEL_19;
          }
          v11 = BDECFG_EVT_PREPARE_DRIVE_ERROR;
          v5 = 14;
        }
        else
        {
          v11 = BDECFG_EVT_CREATE_DRIVE_ERROR;
          v5 = 13;
        }
      }
      else
      {
        v11 = BDECFG_EVT_SHRINK_DRIVE_ERROR;
        v5 = 12;
      }
LABEL_20:
      v18[0] = 16;
      v18[2] = v5;
      v18[1] = 1;
      v18[4] = 16;
      v18[6] = a2;
      v18[5] = 1;
      WinSqmAddToStreamEx(0, 4464, 2, v18, 0);
LABEL_21:
      v12 = EventWrite(g_EventRegistrationHandle, (PCEVENT_DESCRIPTOR)v11, 2u, &UserData);
      if ( v12 )
      {
        if ( v12 > 0 )
          v6 = (unsigned __int16)v12 | 0x80070000;
        else
          v6 = v12;
        v16 = v6;
      }
      goto LABEL_26;
    }
    v11 = BDECFG_EVT_INIT_ERROR;
    v5 = 11;
LABEL_19:
    if ( !v5 )
      goto LABEL_21;
    goto LABEL_20;
  }
LABEL_26:
  if ( *(_QWORD *)Buffer )
    LocalFree(*(HLOCAL *)Buffer);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000e300  mov     r11, rsp
0x18000e303  push    rbx
0x18000e304  push    rsi
0x18000e305  push    rdi
0x18000e306  push    r15
0x18000e308  sub     rsp, 0A8h
0x18000e30f  mov     rax, cs:__security_cookie
0x18000e316  xor     rax, rsp
0x18000e319  mov     [rsp+0C8h+var_30], rax
0x18000e321  mov     r15d, edx
0x18000e324  mov     edi, ecx
0x18000e326  mov     r8d, edx
0x18000e329  mov     [rsp+0C8h+var_88], edx
0x18000e32d  mov     qword ptr [r11-78h], 0
0x18000e335  xor     esi, esi
0x18000e337  xor     ebx, ebx
0x18000e339  mov     eax, 0C0A00016h
0x18000e33e  cmp     cs:?g_EventRegistrationHandle@@3_KA, rbx; unsigned __int64 g_EventRegistrationHandle
0x18000e345  cmovz   ebx, eax
0x18000e348  mov     [rsp+0C8h+var_7C], ebx
0x18000e34c  test    ebx, ebx
0x18000e34e  js      loc_18000E4DC
0x18000e354  mov     [rsp+0C8h+var_80], 1
0x18000e35c  lea     rax, [rsp+0C8h+var_88]
0x18000e361  mov     [r11-50h], rax
0x18000e365  mov     qword ptr [r11-48h], 4
0x18000e36d  mov     eax, edx
0x18000e36f  and     eax, 1FFF0000h
0x18000e374  cmp     eax, 70000h
0x18000e379  jnz     short loc_18000E388
0x18000e37b  test    edx, edx
0x18000e37d  jns     short loc_18000E388
0x18000e37f  movzx   r8d, r15w; dwMessageId
0x18000e383  mov     [rsp+0C8h+var_88], r8d
0x18000e388  mov     [rsp+0C8h+Arguments], 0; Arguments
0x18000e391  mov     [rsp+0C8h+nSize], 0; nSize
0x18000e399  lea     rax, [rsp+0C8h+Buffer]
0x18000e39e  mov     [rsp+0C8h+lpBuffer], rax; lpBuffer
0x18000e3a3  xor     r9d, r9d; dwLanguageId
0x18000e3a6  mov     rdx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; lpSource
0x18000e3ad  mov     ecx, 1BFFh; dwFlags
0x18000e3b2  call    cs:__imp_FormatMessageW
0x18000e3b8  mov     ecx, eax
0x18000e3ba  mov     [rsp+0C8h+var_80], 2
0x18000e3c2  test    eax, eax
0x18000e3c4  jnz     short loc_18000E3E9
0x18000e3c6  lea     rax, word_180017638
0x18000e3cd  mov     [rsp+0C8h+var_40], rax
0x18000e3d5  mov     [rsp+0C8h+var_38], 2
0x18000e3e1  xor     ebx, ebx
0x18000e3e3  mov     [rsp+0C8h+var_7C], ebx
0x18000e3e7  jmp     short loc_18000E40F
0x18000e3e9  mov     rax, qword ptr [rsp+0C8h+Buffer]
0x18000e3ee  mov     [rsp+0C8h+var_40], rax
0x18000e3f6  lea     eax, ds:2[rcx*2]
0x18000e3fd  mov     dword ptr [rsp+0C8h+var_38], eax
0x18000e404  mov     dword ptr [rsp+0C8h+var_38+4], 0
0x18000e40f  sub     edi, 1
0x18000e412  jz      short loc_18000E456
0x18000e414  sub     edi, 1
0x18000e417  jz      short loc_18000E448
0x18000e419  sub     edi, 1
0x18000e41c  jz      short loc_18000E43A
0x18000e41e  cmp     edi, 1
0x18000e421  jz      short loc_18000E42C
0x18000e423  lea     rdi, BDECFG_EVT_TOOL_ERROR
0x18000e42a  jmp     short loc_18000E462
0x18000e42c  lea     rdi, BDECFG_EVT_PREPARE_DRIVE_ERROR
0x18000e433  mov     esi, 0Eh
0x18000e438  jmp     short loc_18000E466
0x18000e43a  lea     rdi, BDECFG_EVT_CREATE_DRIVE_ERROR
0x18000e441  mov     esi, 0Dh
0x18000e446  jmp     short loc_18000E466
0x18000e448  lea     rdi, BDECFG_EVT_SHRINK_DRIVE_ERROR
0x18000e44f  mov     esi, 0Ch
0x18000e454  jmp     short loc_18000E466
0x18000e456  lea     rdi, BDECFG_EVT_INIT_ERROR
0x18000e45d  mov     esi, 0Bh
0x18000e462  test    esi, esi
0x18000e464  jz      short loc_18000E4AA
0x18000e466  mov     eax, 10h
0x18000e46b  mov     [rsp+0C8h+var_70], eax
0x18000e46f  mov     [rsp+0C8h+var_68], esi
0x18000e473  mov     [rsp+0C8h+var_6C], 1
0x18000e47b  mov     [rsp+0C8h+var_60], eax
0x18000e47f  mov     [rsp+0C8h+var_58], r15d
0x18000e484  mov     [rsp+0C8h+var_5C], 1
0x18000e48c  mov     dword ptr [rsp+0C8h+lpBuffer], 0
0x18000e494  lea     r9, [rsp+0C8h+var_70]
0x18000e499  mov     edx, 1170h
0x18000e49e  xor     ecx, ecx
0x18000e4a0  lea     r8d, [rax-0Eh]
0x18000e4a4  call    cs:__imp_WinSqmAddToStreamEx
0x18000e4aa  lea     r9, [rsp+0C8h+UserData]; UserData
0x18000e4af  mov     r8d, 2; UserDataCount
0x18000e4b5  mov     rdx, rdi; EventDescriptor
0x18000e4b8  mov     rcx, cs:?g_EventRegistrationHandle@@3_KA; RegHandle
0x18000e4bf  call    cs:__imp_EventWrite
0x18000e4c5  test    eax, eax
0x18000e4c7  jz      short loc_18000E4DC
0x18000e4c9  jg      short loc_18000E4CF
0x18000e4cb  mov     ebx, eax
0x18000e4cd  jmp     short loc_18000E4D8
0x18000e4cf  movzx   ebx, ax
0x18000e4d2  or      ebx, 80070000h
0x18000e4d8  mov     [rsp+0C8h+var_7C], ebx
0x18000e4dc  mov     rcx, qword ptr [rsp+0C8h+Buffer]; hMem
0x18000e4e1  test    rcx, rcx
0x18000e4e4  jz      short loc_18000E4EC
0x18000e4e6  call    cs:__imp_LocalFree
0x18000e4ec  mov     eax, ebx
0x18000e4ee  mov     rcx, [rsp+0C8h+var_30]
0x18000e4f6  xor     rcx, rsp; StackCookie
0x18000e4f9  call    __security_check_cookie
0x18000e4fe  add     rsp, 0A8h
0x18000e505  pop     r15
0x18000e507  pop     rdi
0x18000e508  pop     rsi
0x18000e509  pop     rbx
0x18000e50a  retn
0x1800142e0  push    rbp
0x1800142e2  sub     rsp, 40h
0x1800142e6  mov     rbp, rdx
0x1800142e9  mov     rcx, [rbp+50h]; hMem
0x1800142ed  test    rcx, rcx
0x1800142f0  jz      short loc_1800142F9
0x1800142f2  call    cs:__imp_LocalFree
0x1800142f8  nop
0x1800142f9  add     rsp, 40h
0x1800142fd  pop     rbp
0x1800142fe  retn
```
