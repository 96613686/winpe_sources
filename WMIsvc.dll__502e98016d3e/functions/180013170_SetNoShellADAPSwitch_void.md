# SetNoShellADAPSwitch(void)

- ea: `0x180013170`
- end: `0x180013233`
- name: `?SetNoShellADAPSwitch@@YAXXZ`
- size: `195`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b760`

## callees

- `0x180012c34`
- `0x180013170`

## import_xrefs

- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180013228`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180013228`
- `wbemcomn!??0Registry@@QEAA@PEAUHKEY__@@KKPEBG@Z` at `0x180013198`
- `wbemcomn!??0Registry@@QEAA@PEAUHKEY__@@KKPEBG@Z` at `0x180013198`
- `wbemcomn!?SetDWORD@Registry@@QEAAHPEBGK@Z` at `0x1800131b9`
- `wbemcomn!?SetDWORD@Registry@@QEAAHPEBGK@Z` at `0x1800131b9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void SetNoShellADAPSwitch(void)
{
  __int64 v0; // r9
  _QWORD *v1; // rcx
  __int64 v2; // rdx
  _BYTE v3[20]; // [rsp+30h] [rbp-28h] BYREF
  unsigned int v4; // [rsp+44h] [rbp-14h]

  Registry::Registry((Registry *)v3, HKEY_LOCAL_MACHINE, 1u, 0x2001Fu, L"Software\\Microsoft\\WBEM\\CIMOM\\ADAP");
  v0 = v4;
  if ( v4 )
  {
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v2 = 14;
      goto LABEL_11;
    }
  }
  else if ( Registry::SetDWORD((Registry *)v3, L"NoShell", 1u) )
  {
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v2 = 13;
      v0 = v4;
LABEL_11:
      WPP_SF_d(v1[2], v2, WPP_1ead9032b647397af64ee4622953436c_Traceguids, v0);
    }
  }
  Registry::~Registry((Registry *)v3);
}

```

## disassembly

```asm
0x180013170  sub     rsp, 58h
0x180013174  lea     rax, aSoftwareMicros_2; "Software\\Microsoft\\WBEM\\CIMOM\\ADAP"
0x18001317b  mov     [rsp+58h+var_38], rax
0x180013180  mov     rdx, 0FFFFFFFF80000002h
0x180013187  mov     r9d, 2001Fh
0x18001318d  mov     r8d, 1
0x180013193  lea     rcx, [rsp+58h+var_28]
0x180013198  call    cs:__imp_??0Registry@@QEAA@PEAUHKEY__@@KKPEBG@Z; Registry::Registry(HKEY__ *,ulong,ulong,ushort const *)
0x18001319e  nop
0x18001319f  mov     r9d, [rsp+58h+var_14]
0x1800131a4  test    r9d, r9d
0x1800131a7  jnz     short loc_1800131EE
0x1800131a9  lea     r8d, [r9+1]
0x1800131ad  lea     rdx, aNoshell; "NoShell"
0x1800131b4  lea     rcx, [rsp+58h+var_28]
0x1800131b9  call    cs:__imp_?SetDWORD@Registry@@QEAAHPEBGK@Z; Registry::SetDWORD(ushort const *,ulong)
0x1800131bf  test    eax, eax
0x1800131c1  jz      short loc_180013223
0x1800131c3  lea     rax, WPP_GLOBAL_Control
0x1800131ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800131d1  cmp     rcx, rax
0x1800131d4  jz      short loc_180013223
0x1800131d6  test    byte ptr [rcx+1Ch], 1
0x1800131da  jz      short loc_180013223
0x1800131dc  cmp     byte ptr [rcx+19h], 5
0x1800131e0  jb      short loc_180013223
0x1800131e2  mov     edx, 0Dh
0x1800131e7  mov     r9d, [rsp+58h+var_14]
0x1800131ec  jmp     short loc_180013212
0x1800131ee  lea     rax, WPP_GLOBAL_Control
0x1800131f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800131fc  cmp     rcx, rax
0x1800131ff  jz      short loc_180013223
0x180013201  test    byte ptr [rcx+1Ch], 1
0x180013205  jz      short loc_180013223
0x180013207  cmp     byte ptr [rcx+19h], 5
0x18001320b  jb      short loc_180013223
0x18001320d  mov     edx, 0Eh
0x180013212  lea     r8, WPP_1ead9032b647397af64ee4622953436c_Traceguids
0x180013219  mov     rcx, [rcx+10h]
0x18001321d  call    WPP_SF_d
0x180013222  nop
0x180013223  lea     rcx, [rsp+58h+var_28]
0x180013228  call    cs:__imp_??1Registry@@QEAA@XZ; Registry::~Registry(void)
0x18001322e  add     rsp, 58h
0x180013232  retn
```
