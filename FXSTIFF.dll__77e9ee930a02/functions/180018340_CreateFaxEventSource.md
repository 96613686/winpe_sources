# CreateFaxEventSource

- ea: `0x180018340`
- end: `0x180018579`
- name: `CreateFaxEventSource`
- size: `569`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017744`

## callees

- `0x180009f04`
- `0x180009f34`
- `0x18000f128`
- `0x18000f454`
- `0x18000f940`
- `0x18000fa34`
- `0x180017098`
- `0x180018340`
- `0x1800189d0`

## import_xrefs

- `msvcrt!_itow` at `0x180018487`
- `msvcrt!_itow` at `0x180018487`
- `KERNEL32!GetLastError` at `0x1800183ea`
- `KERNEL32!GetLastError` at `0x1800183ea`
- `ADVAPI32!RegCloseKey` at `0x180018458`
- `ADVAPI32!RegCloseKey` at `0x18001851f`
- `ADVAPI32!RegCloseKey` at `0x180018541`
- `ADVAPI32!RegCloseKey` at `0x180018458`
- `ADVAPI32!RegCloseKey` at `0x18001851f`
- `ADVAPI32!RegCloseKey` at `0x180018541`

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
0x180018340  mov     [rsp+arg_10], rbx
0x180018345  mov     [rsp+arg_18], rbp
0x18001834a  push    rsi
0x18001834b  push    rdi
0x18001834c  push    r12
0x18001834e  push    r14
0x180018350  push    r15
0x180018352  sub     rsp, 60h
0x180018356  mov     rax, cs:__security_cookie
0x18001835d  xor     rax, rsp
0x180018360  mov     [rsp+88h+var_38], rax
0x180018365  mov     r12, rdx
0x180018368  mov     rsi, rcx
0x18001836b  mov     rcx, cs:WPP_GLOBAL_Control
0x180018372  lea     rbp, WPP_GLOBAL_Control
0x180018379  lea     r14, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x180018380  mov     bl, 2
0x180018382  cmp     rcx, rbp
0x180018385  jz      short loc_1800183A3
0x180018387  test    [rcx+1Ch], bl
0x18001838a  jz      short loc_1800183A3
0x18001838c  cmp     byte ptr [rcx+19h], 5
0x180018390  jb      short loc_1800183A3
0x180018392  mov     rcx, [rcx+10h]
0x180018396  mov     edx, 21h ; '!'
0x18001839b  mov     r8, r14
0x18001839e  call    WPP_SF_
0x1800183a3  cmp     dword ptr [rsi+38h], 0
0x1800183a7  jnz     loc_18001854D
0x1800183ad  mov     r9d, 20006h
0x1800183b3  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Fax\\Logging"
0x1800183ba  mov     r8d, 1
0x1800183c0  mov     rcx, 0FFFFFFFF80000002h
0x1800183c7  call    OpenRegistryKey
0x1800183cc  mov     rdi, rax
0x1800183cf  test    rax, rax
0x1800183d2  jnz     short loc_180018416
0x1800183d4  mov     rax, cs:WPP_GLOBAL_Control
0x1800183db  cmp     rax, rbp
0x1800183de  jz      short loc_18001840F
0x1800183e0  test    [rax+1Ch], bl
0x1800183e3  jz      short loc_18001840F
0x1800183e5  cmp     [rax+19h], bl
0x1800183e8  jb      short loc_18001840F
0x1800183ea  call    cs:__imp_GetLastError
0x1800183f1  nop     dword ptr [rax+rax+00h]
0x1800183f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800183fd  lea     edx, [rdi+22h]
0x180018400  mov     r9d, eax
0x180018403  mov     r8, r14
0x180018406  mov     rcx, [rcx+10h]
0x18001840a  call    WPP_SF_d
0x18001840f  xor     eax, eax
0x180018411  jmp     loc_180018552
0x180018416  mov     r15d, 40h ; '@'
0x18001841c  mov     ecx, r15d; dwBytes
0x18001841f  call    pMemAlloc
0x180018424  mov     [rsi+30h], rax
0x180018428  test    rax, rax
0x18001842b  jnz     short loc_180018466
0x18001842d  mov     rcx, cs:WPP_GLOBAL_Control
0x180018434  cmp     rcx, rbp
0x180018437  jz      short loc_180018455
0x180018439  test    [rcx+1Ch], bl
0x18001843c  jz      short loc_180018455
0x18001843e  cmp     [rcx+19h], bl
0x180018441  jb      short loc_180018455
0x180018443  mov     rcx, [rcx+10h]
0x180018447  lea     edx, [rax+23h]
0x18001844a  mov     r9d, r15d
0x18001844d  mov     r8, r14
0x180018450  call    WPP_SF_d
0x180018455  mov     rcx, rdi; hKey
0x180018458  call    cs:__imp_RegCloseKey
0x18001845f  nop     dword ptr [rax+rax+00h]
0x180018464  jmp     short loc_18001840F
0x180018466  xor     ebp, ebp
0x180018468  xor     r14d, r14d
0x18001846b  xorps   xmm0, xmm0
0x18001846e  lea     rdx, [rsp+88h+Buffer]; Buffer
0x180018473  inc     ebp
0x180018475  mov     r8d, 0Ah; Radix
0x18001847b  mov     ecx, ebp; Value
0x18001847d  movups  xmmword ptr [rsp+88h+Buffer], xmm0
0x180018482  movups  [rsp+88h+var_48], xmm0
0x180018487  call    cs:__imp__itow
0x18001848e  nop     dword ptr [rax+rax+00h]
0x180018493  mov     r9d, 20006h
0x180018499  lea     rdx, [rsp+88h+Buffer]
0x18001849e  mov     r8d, 1
0x1800184a4  mov     rcx, rdi
0x1800184a7  call    OpenRegistryKey
0x1800184ac  mov     r15, rax
0x1800184af  test    rax, rax
0x1800184b2  jz      short loc_18001852B
0x1800184b4  mov     rbx, r14
0x1800184b7  mov     rcx, rax; HKEY
0x1800184ba  add     rbx, rbx
0x1800184bd  mov     r9, [r12+rbx*8]; unsigned __int16 *
0x1800184c1  call    ?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z; SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)
0x1800184c6  mov     rcx, [r12+rbx*8]; unsigned __int16 *
0x1800184ca  call    StringDup
0x1800184cf  mov     rcx, rax
0x1800184d2  lea     rdx, aLevel; "Level"
0x1800184d9  mov     rax, [rsi+30h]
0x1800184dd  mov     [rax+rbx*8], rcx
0x1800184e1  mov     rcx, r15
0x1800184e4  mov     r8d, [r12+rbx*8+0Ch]
0x1800184e9  call    SetRegistryDword
0x1800184ee  mov     rcx, [rsi+30h]
0x1800184f2  lea     rdx, aNumber; "Number"
0x1800184f9  mov     eax, [r12+rbx*8+0Ch]
0x1800184fe  mov     [rcx+rbx*8+0Ch], eax
0x180018502  mov     rcx, r15
0x180018505  mov     r8d, [r12+rbx*8+8]
0x18001850a  call    SetRegistryDword
0x18001850f  mov     rcx, [rsi+30h]
0x180018513  mov     eax, [r12+rbx*8+8]
0x180018518  mov     [rcx+rbx*8+8], eax
0x18001851c  mov     rcx, r15; hKey
0x18001851f  call    cs:__imp_RegCloseKey
0x180018526  nop     dword ptr [rax+rax+00h]
0x18001852b  inc     r14
0x18001852e  cmp     ebp, 4
0x180018531  jb      loc_18001846B
0x180018537  mov     rcx, rdi; hKey
0x18001853a  mov     dword ptr [rsi+38h], 4
0x180018541  call    cs:__imp_RegCloseKey
0x180018548  nop     dword ptr [rax+rax+00h]
0x18001854d  mov     eax, 1
0x180018552  mov     rcx, [rsp+88h+var_38]
0x180018557  xor     rcx, rsp; StackCookie
0x18001855a  call    __security_check_cookie
0x18001855f  lea     r11, [rsp+88h+var_28]
0x180018564  mov     rbx, [r11+40h]
0x180018568  mov     rbp, [r11+48h]
0x18001856c  mov     rsp, r11
0x18001856f  pop     r15
0x180018571  pop     r14
0x180018573  pop     r12
0x180018575  pop     rdi
0x180018576  pop     rsi
0x180018577  retn
```
