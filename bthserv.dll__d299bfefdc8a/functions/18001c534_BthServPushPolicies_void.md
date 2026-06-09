# BthServPushPolicies(void)

- ea: `0x18001c534`
- end: `0x18001c7e9`
- name: `?BthServPushPolicies@@YAXXZ`
- size: `693`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800100c0`
- `0x18001cfe0`

## callees

- `0x1800110fc`
- `0x180011194`
- `0x18001c534`
- `0x18001c994`
- `0x1800303ec`
- `0x180030dd4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001c5b9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001c5b9`
- `ntdll!RtlPublishWnfStateData` at `0x18001c780`
- `ntdll!RtlPublishWnfStateData` at `0x18001c780`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c6ed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c6ed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c599`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c599`

## pseudocode

```c
void BthServPushPolicies(void)
{
  int v0; // edx
  int v1; // r8d
  int PolicyRegistryLocation; // ebx
  LSTATUS v3; // eax
  int v4; // ebx
  int v5; // edx
  int v6; // r8d
  char v7; // di
  bool v8; // dl
  int v9; // edx
  int v10; // r8d
  int v11; // edx
  int v12; // r8d
  int phkResult; // [rsp+20h] [rbp-58h]
  int v14; // [rsp+28h] [rbp-50h]
  LPCWSTR lpSubKey[2]; // [rsp+50h] [rbp-28h] BYREF
  int v16; // [rsp+80h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+10h] BYREF

  if ( (int)BthSyncWithPolicyManager() < 0 )
  {
    v7 = 1;
    LOBYTE(v0) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
    if ( (_BYTE)v0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v1) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v0,
        v1,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        phkResult,
        v14,
        24,
        (__int64)WPP_1ad68b0ce8773238920c85c6e45f2d1d_Traceguids);
    }
  }
  else
  {
    hKey = 0;
    *(_OWORD *)lpSubKey = 0;
    PolicyRegistryLocation = BthGetPolicyRegistryLocation((PUNICODE_STRING)lpSubKey);
    if ( PolicyRegistryLocation < 0 )
    {
      v4 = PolicyRegistryLocation | 0x10000000;
    }
    else
    {
      v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[1], 0, 0x20006u, &hKey);
      v4 = v3;
      if ( v3 > 0 )
        v4 = (unsigned __int16)v3 | 0x80070000;
    }
    free((void *)lpSubKey[1]);
    if ( v4 < 0 )
    {
      v7 = 1;
      LOBYTE(v5) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
      if ( (_BYTE)v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v5,
          v6,
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          phkResult,
          v14,
          23,
          (__int64)WPP_1ad68b0ce8773238920c85c6e45f2d1d_Traceguids);
      }
    }
    else
    {
      v7 = 1;
      v8 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
      if ( v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, v6, *((_QWORD *)WPP_GLOBAL_Control + 5));
      }
      if ( (int)BthServReplicatePolicies(hKey) < 0 )
      {
        LOBYTE(v9) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
        if ( (_BYTE)v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v9,
            v10,
            *((_QWORD *)WPP_GLOBAL_Control + 5),
            phkResult,
            v14,
            22,
            (__int64)WPP_1ad68b0ce8773238920c85c6e45f2d1d_Traceguids);
        }
      }
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  v16 = 1;
  if ( (int)RtlPublishWnfStateData(WNF_ENTR_BLUETOOTH_POLICY_VALUE_CHANGED, 0, &v16, 4) < 0 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      v7 = 0;
    if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = v7;
      LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v11,
        v12,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        0,
        v14,
        25,
        (__int64)WPP_1ad68b0ce8773238920c85c6e45f2d1d_Traceguids);
    }
  }
}

```

## disassembly

```asm
0x18001c534  mov     [rsp+arg_10], rbx
0x18001c539  mov     [rsp+arg_18], rbp
0x18001c53e  push    rsi
0x18001c53f  push    rdi
0x18001c540  push    r14
0x18001c542  sub     rsp, 60h
0x18001c546  call    BthSyncWithPolicyManager
0x18001c54b  test    eax, eax
0x18001c54d  js      loc_18001C6F5
0x18001c553  mov     [rsp+78h+hKey], 0
0x18001c55f  xorps   xmm0, xmm0
0x18001c562  movups  xmmword ptr [rsp+78h+lpSubKey], xmm0
0x18001c567  lea     rcx, [rsp+78h+lpSubKey]; DestinationString
0x18001c56c  call    BthGetPolicyRegistryLocation
0x18001c571  mov     ebx, eax
0x18001c573  test    eax, eax
0x18001c575  js      short loc_18001C5B0
0x18001c577  lea     rax, [rsp+78h+hKey]
0x18001c57f  mov     [rsp+78h+phkResult], rax; phkResult
0x18001c584  mov     r9d, 20006h; samDesired
0x18001c58a  xor     r8d, r8d; ulOptions
0x18001c58d  mov     rdx, [rsp+78h+lpSubKey+8]; lpSubKey
0x18001c592  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001c599  call    cs:__imp_RegOpenKeyExW
0x18001c59f  mov     ebx, eax
0x18001c5a1  test    eax, eax
0x18001c5a3  jle     short loc_18001C5B4
0x18001c5a5  movzx   ebx, ax
0x18001c5a8  or      ebx, 80070000h
0x18001c5ae  jmp     short loc_18001C5B4
0x18001c5b0  bts     ebx, 1Ch
0x18001c5b4  mov     rcx, [rsp+78h+lpSubKey+8]; Block
0x18001c5b9  call    cs:__imp_free
0x18001c5bf  test    ebx, ebx
0x18001c5c1  js      loc_18001C67B
0x18001c5c7  lea     rsi, WPP_GLOBAL_Control
0x18001c5ce  mov     edi, 1
0x18001c5d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c5da  cmp     rcx, rsi
0x18001c5dd  jz      short loc_18001C5EA
0x18001c5df  cmp     byte ptr [rcx+19h], 4
0x18001c5e3  jb      short loc_18001C5EA
0x18001c5e5  mov     dl, dil
0x18001c5e8  jmp     short loc_18001C5EC
0x18001c5ea  xor     dl, dl
0x18001c5ec  lea     rbp, WPP_RECORDER_INITIALIZED
0x18001c5f3  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18001c5fa  setnz   r8b
0x18001c5fe  lea     r14, WPP_1ad68b0ce8773238920c85c6e45f2d1d_Traceguids
0x18001c605  test    dl, dl
0x18001c607  jnz     short loc_18001C60E
0x18001c609  test    r8b, r8b
0x18001c60c  jz      short loc_18001C627
0x18001c60e  mov     [rsp+78h+var_40], r14
0x18001c613  mov     [rsp+78h+var_48], 15h
0x18001c61a  mov     r9, [rcx+28h]
0x18001c61e  mov     rcx, [rcx+10h]
0x18001c622  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001c627  mov     rcx, [rsp+78h+hKey]; hKey
0x18001c62f  call    BthServReplicatePolicies
0x18001c634  test    eax, eax
0x18001c636  jns     loc_18001C6E0
0x18001c63c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c643  cmp     rcx, rsi
0x18001c646  jz      short loc_18001C653
0x18001c648  cmp     byte ptr [rcx+19h], 2
0x18001c64c  jb      short loc_18001C653
0x18001c64e  mov     dl, dil
0x18001c651  jmp     short loc_18001C655
0x18001c653  xor     dl, dl
0x18001c655  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18001c65c  setnz   r8b
0x18001c660  test    dl, dl
0x18001c662  jnz     short loc_18001C669
0x18001c664  test    r8b, r8b
0x18001c667  jz      short loc_18001C6E0
0x18001c669  mov     [rsp+78h+var_30], eax
0x18001c66d  mov     [rsp+78h+var_40], r14
0x18001c672  mov     [rsp+78h+var_48], 16h
0x18001c679  jmp     short loc_18001C6D2
0x18001c67b  lea     rsi, WPP_GLOBAL_Control
0x18001c682  mov     edi, 1
0x18001c687  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c68e  cmp     rcx, rsi
0x18001c691  jz      short loc_18001C69E
0x18001c693  cmp     byte ptr [rcx+19h], 2
0x18001c697  jb      short loc_18001C69E
0x18001c699  mov     dl, dil
0x18001c69c  jmp     short loc_18001C6A0
0x18001c69e  xor     dl, dl
0x18001c6a0  lea     rbp, WPP_RECORDER_INITIALIZED
0x18001c6a7  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18001c6ae  setnz   r8b
0x18001c6b2  lea     r14, WPP_1ad68b0ce8773238920c85c6e45f2d1d_Traceguids
0x18001c6b9  test    dl, dl
0x18001c6bb  jnz     short loc_18001C6C2
0x18001c6bd  test    r8b, r8b
0x18001c6c0  jz      short loc_18001C6E0
0x18001c6c2  mov     [rsp+78h+var_30], ebx
0x18001c6c6  mov     [rsp+78h+var_40], r14
0x18001c6cb  mov     [rsp+78h+var_48], 17h
0x18001c6d2  mov     r9, [rcx+28h]
0x18001c6d6  mov     rcx, [rcx+10h]
0x18001c6da  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18001c6df  nop
0x18001c6e0  mov     rcx, [rsp+78h+hKey]; hKey
0x18001c6e8  test    rcx, rcx
0x18001c6eb  jz      short loc_18001C759
0x18001c6ed  call    cs:__imp_RegCloseKey
0x18001c6f3  jmp     short loc_18001C759
0x18001c6f5  lea     rsi, WPP_GLOBAL_Control
0x18001c6fc  mov     edi, 1
0x18001c701  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c708  cmp     rcx, rsi
0x18001c70b  jz      short loc_18001C718
0x18001c70d  cmp     byte ptr [rcx+19h], 2
0x18001c711  jb      short loc_18001C718
0x18001c713  mov     dl, dil
0x18001c716  jmp     short loc_18001C71A
0x18001c718  xor     dl, dl
0x18001c71a  lea     rbp, WPP_RECORDER_INITIALIZED
0x18001c721  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18001c728  setnz   r8b
0x18001c72c  lea     r14, WPP_1ad68b0ce8773238920c85c6e45f2d1d_Traceguids
0x18001c733  test    dl, dl
0x18001c735  jnz     short loc_18001C73C
0x18001c737  test    r8b, r8b
0x18001c73a  jz      short loc_18001C759
0x18001c73c  mov     [rsp+78h+var_30], eax
0x18001c740  mov     [rsp+78h+var_40], r14
0x18001c745  mov     [rsp+78h+var_48], 18h
0x18001c74c  mov     r9, [rcx+28h]
0x18001c750  mov     rcx, [rcx+10h]
0x18001c754  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18001c759  mov     [rsp+78h+arg_0], edi
0x18001c760  mov     [rsp+78h+phkResult], 0
0x18001c769  mov     r9d, 4
0x18001c76f  lea     r8, [rsp+78h+arg_0]
0x18001c777  xor     edx, edx
0x18001c779  mov     rcx, cs:WNF_ENTR_BLUETOOTH_POLICY_VALUE_CHANGED
0x18001c780  call    cs:__imp_RtlPublishWnfStateData
0x18001c786  test    eax, eax
0x18001c788  jns     short loc_18001C7D4
0x18001c78a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c791  cmp     rcx, rsi
0x18001c794  jz      short loc_18001C79C
0x18001c796  cmp     byte ptr [rcx+19h], 2
0x18001c79a  jnb     short loc_18001C79F
0x18001c79c  xor     dil, dil
0x18001c79f  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18001c7a6  setnz   r8b
0x18001c7aa  test    dil, dil
0x18001c7ad  jnz     short loc_18001C7B4
0x18001c7af  test    r8b, r8b
0x18001c7b2  jz      short loc_18001C7D4
0x18001c7b4  mov     [rsp+78h+var_30], eax
0x18001c7b8  mov     [rsp+78h+var_40], r14
0x18001c7bd  mov     [rsp+78h+var_48], 19h
0x18001c7c4  mov     r9, [rcx+28h]
0x18001c7c8  mov     dl, dil
0x18001c7cb  mov     rcx, [rcx+10h]
0x18001c7cf  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18001c7d4  lea     r11, [rsp+78h+var_18]
0x18001c7d9  mov     rbx, [r11+30h]
0x18001c7dd  mov     rbp, [r11+38h]
0x18001c7e1  mov     rsp, r11
0x18001c7e4  pop     r14
0x18001c7e6  pop     rdi
0x18001c7e7  pop     rsi
0x18001c7e8  retn
```
