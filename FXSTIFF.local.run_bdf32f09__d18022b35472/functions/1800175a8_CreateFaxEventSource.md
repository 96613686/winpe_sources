# CreateFaxEventSource

- ea: `0x1800175a8`
- end: `0x1800177c2`
- name: `CreateFaxEventSource`
- size: `538`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016a08`

## callees

- `0x180009a7c`
- `0x180009aa4`
- `0x18000ea18`
- `0x18000ed20`
- `0x18000f1b4`
- `0x18000f290`
- `0x18001639c`
- `0x1800175a8`
- `0x180017c00`

## import_xrefs

- `msvcrt!_itow` at `0x1800176e3`
- `msvcrt!_itow` at `0x1800176e3`
- `KERNEL32!GetLastError` at `0x180017652`
- `KERNEL32!GetLastError` at `0x180017652`
- `ADVAPI32!RegCloseKey` at `0x1800176ba`
- `ADVAPI32!RegCloseKey` at `0x180017775`
- `ADVAPI32!RegCloseKey` at `0x180017791`
- `ADVAPI32!RegCloseKey` at `0x1800176ba`
- `ADVAPI32!RegCloseKey` at `0x180017775`
- `ADVAPI32!RegCloseKey` at `0x180017791`

## pseudocode

```c
__int64 __fastcall CreateFaxEventSource(__int64 a1, __int64 a2)
{
  HKEY v4; // rdi
  DWORD LastError; // eax
  LPVOID v7; // rax
  unsigned int v8; // ebp
  __int64 v9; // r14
  HKEY v10; // rax
  __int64 v11; // rdx
  const unsigned __int16 *v12; // r8
  HKEY v13; // r15
  wchar_t Buffer[8]; // [rsp+30h] [rbp-58h] BYREF
  __int128 v15; // [rsp+40h] [rbp-48h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids);
  }
  if ( !*(_DWORD *)(a1 + 56) )
  {
    v4 = OpenRegistryKey(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Fax\\Logging", 1, 0x20006u);
    if ( !v4 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, LastError);
      }
      return 0;
    }
    v7 = pMemAlloc(0x40u);
    *(_QWORD *)(a1 + 48) = v7;
    if ( !v7 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, 64);
      }
      RegCloseKey(v4);
      return 0;
    }
    v8 = 0;
    v9 = 0;
    do
    {
      ++v8;
      *(_OWORD *)Buffer = 0;
      v15 = 0;
      _itow(v8, Buffer, 10);
      v10 = OpenRegistryKey(v4, Buffer, 1, 0x20006u);
      v13 = v10;
      if ( v10 )
      {
        SetRegistryStringValue(v10, v11, v12, *(const BYTE **)(a2 + 16 * v9));
        *(_QWORD *)(*(_QWORD *)(a1 + 48) + 16 * v9) = StringDup(*(unsigned __int16 **)(a2 + 16 * v9));
        SetRegistryDword(v13, L"Level", *(_DWORD *)(a2 + 16 * v9 + 12));
        *(_DWORD *)(*(_QWORD *)(a1 + 48) + 16 * v9 + 12) = *(_DWORD *)(a2 + 16 * v9 + 12);
        SetRegistryDword(v13, L"Number", *(_DWORD *)(a2 + 16 * v9 + 8));
        *(_DWORD *)(*(_QWORD *)(a1 + 48) + 16 * v9 + 8) = *(_DWORD *)(a2 + 16 * v9 + 8);
        RegCloseKey(v13);
      }
      ++v9;
    }
    while ( v8 < 4 );
    *(_DWORD *)(a1 + 56) = 4;
    RegCloseKey(v4);
  }
  return 1;
}

```

## disassembly

```asm
0x1800175a8  mov     [rsp+arg_10], rbx
0x1800175ad  mov     [rsp+arg_18], rbp
0x1800175b2  push    rsi
0x1800175b3  push    rdi
0x1800175b4  push    r12
0x1800175b6  push    r14
0x1800175b8  push    r15
0x1800175ba  sub     rsp, 60h
0x1800175be  mov     rax, cs:__security_cookie
0x1800175c5  xor     rax, rsp
0x1800175c8  mov     [rsp+88h+var_38], rax
0x1800175cd  mov     r12, rdx
0x1800175d0  mov     rsi, rcx
0x1800175d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800175da  lea     rbp, WPP_GLOBAL_Control
0x1800175e1  lea     r14, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x1800175e8  mov     bl, 2
0x1800175ea  cmp     rcx, rbp
0x1800175ed  jz      short loc_18001760B
0x1800175ef  test    [rcx+1Ch], bl
0x1800175f2  jz      short loc_18001760B
0x1800175f4  cmp     byte ptr [rcx+19h], 5
0x1800175f8  jb      short loc_18001760B
0x1800175fa  mov     rcx, [rcx+10h]
0x1800175fe  mov     edx, 21h ; '!'
0x180017603  mov     r8, r14
0x180017606  call    WPP_SF_
0x18001760b  cmp     dword ptr [rsi+38h], 0
0x18001760f  jnz     loc_180017797
0x180017615  mov     r9d, 20006h
0x18001761b  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Fax\\Logging"
0x180017622  mov     r8d, 1
0x180017628  mov     rcx, 0FFFFFFFF80000002h
0x18001762f  call    OpenRegistryKey
0x180017634  mov     rdi, rax
0x180017637  test    rax, rax
0x18001763a  jnz     short loc_180017678
0x18001763c  mov     rax, cs:WPP_GLOBAL_Control
0x180017643  cmp     rax, rbp
0x180017646  jz      short loc_180017671
0x180017648  test    [rax+1Ch], bl
0x18001764b  jz      short loc_180017671
0x18001764d  cmp     [rax+19h], bl
0x180017650  jb      short loc_180017671
0x180017652  call    cs:__imp_GetLastError
0x180017658  mov     rcx, cs:WPP_GLOBAL_Control
0x18001765f  lea     edx, [rdi+22h]
0x180017662  mov     r9d, eax
0x180017665  mov     r8, r14
0x180017668  mov     rcx, [rcx+10h]
0x18001766c  call    WPP_SF_d
0x180017671  xor     eax, eax
0x180017673  jmp     loc_18001779C
0x180017678  mov     r15d, 40h ; '@'
0x18001767e  mov     ecx, r15d; dwBytes
0x180017681  call    pMemAlloc
0x180017686  mov     [rsi+30h], rax
0x18001768a  test    rax, rax
0x18001768d  jnz     short loc_1800176C2
0x18001768f  mov     rcx, cs:WPP_GLOBAL_Control
0x180017696  cmp     rcx, rbp
0x180017699  jz      short loc_1800176B7
0x18001769b  test    [rcx+1Ch], bl
0x18001769e  jz      short loc_1800176B7
0x1800176a0  cmp     [rcx+19h], bl
0x1800176a3  jb      short loc_1800176B7
0x1800176a5  mov     rcx, [rcx+10h]
0x1800176a9  lea     edx, [rax+23h]
0x1800176ac  mov     r9d, r15d
0x1800176af  mov     r8, r14
0x1800176b2  call    WPP_SF_d
0x1800176b7  mov     rcx, rdi; hKey
0x1800176ba  call    cs:__imp_RegCloseKey
0x1800176c0  jmp     short loc_180017671
0x1800176c2  xor     ebp, ebp
0x1800176c4  xor     r14d, r14d
0x1800176c7  xorps   xmm0, xmm0
0x1800176ca  lea     rdx, [rsp+88h+Buffer]; Buffer
0x1800176cf  inc     ebp
0x1800176d1  mov     r8d, 0Ah; Radix
0x1800176d7  mov     ecx, ebp; Value
0x1800176d9  movups  xmmword ptr [rsp+88h+Buffer], xmm0
0x1800176de  movups  [rsp+88h+var_48], xmm0
0x1800176e3  call    cs:__imp__itow
0x1800176e9  mov     r9d, 20006h
0x1800176ef  lea     rdx, [rsp+88h+Buffer]
0x1800176f4  mov     r8d, 1
0x1800176fa  mov     rcx, rdi
0x1800176fd  call    OpenRegistryKey
0x180017702  mov     r15, rax
0x180017705  test    rax, rax
0x180017708  jz      short loc_18001777B
0x18001770a  mov     rbx, r14
0x18001770d  mov     rcx, rax; HKEY
0x180017710  add     rbx, rbx
0x180017713  mov     r9, [r12+rbx*8]; unsigned __int16 *
0x180017717  call    ?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z; SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)
0x18001771c  mov     rcx, [r12+rbx*8]; unsigned __int16 *
0x180017720  call    StringDup
0x180017725  mov     rcx, rax
0x180017728  lea     rdx, aLevel; "Level"
0x18001772f  mov     rax, [rsi+30h]
0x180017733  mov     [rax+rbx*8], rcx
0x180017737  mov     rcx, r15
0x18001773a  mov     r8d, [r12+rbx*8+0Ch]
0x18001773f  call    SetRegistryDword
0x180017744  mov     rcx, [rsi+30h]
0x180017748  lea     rdx, aNumber; "Number"
0x18001774f  mov     eax, [r12+rbx*8+0Ch]
0x180017754  mov     [rcx+rbx*8+0Ch], eax
0x180017758  mov     rcx, r15
0x18001775b  mov     r8d, [r12+rbx*8+8]
0x180017760  call    SetRegistryDword
0x180017765  mov     rcx, [rsi+30h]
0x180017769  mov     eax, [r12+rbx*8+8]
0x18001776e  mov     [rcx+rbx*8+8], eax
0x180017772  mov     rcx, r15; hKey
0x180017775  call    cs:__imp_RegCloseKey
0x18001777b  inc     r14
0x18001777e  cmp     ebp, 4
0x180017781  jb      loc_1800176C7
0x180017787  mov     rcx, rdi; hKey
0x18001778a  mov     dword ptr [rsi+38h], 4
0x180017791  call    cs:__imp_RegCloseKey
0x180017797  mov     eax, 1
0x18001779c  mov     rcx, [rsp+88h+var_38]
0x1800177a1  xor     rcx, rsp; StackCookie
0x1800177a4  call    __security_check_cookie
0x1800177a9  lea     r11, [rsp+88h+var_28]
0x1800177ae  mov     rbx, [r11+40h]
0x1800177b2  mov     rbp, [r11+48h]
0x1800177b6  mov     rsp, r11
0x1800177b9  pop     r15
0x1800177bb  pop     r14
0x1800177bd  pop     r12
0x1800177bf  pop     rdi
0x1800177c0  pop     rsi
0x1800177c1  retn
```
