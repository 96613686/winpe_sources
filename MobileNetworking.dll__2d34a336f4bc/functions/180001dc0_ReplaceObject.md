# ReplaceObject

- ea: `0x180001dc0`
- end: `0x180002071`
- name: `ReplaceObject`
- size: `689`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, int, int, int, __int64, LPCWSTR StringSecurityDescriptor)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180001dc0`
- `0x180002a40`
- `0x180002b20`
- `0x180002f80`
- `0x180004b80`
- `0x1800085b0`
- `0x180008ff0`
- `0x180009130`

## string_xrefs

- `0x180001f81`: `ReplaceObject`
- `0x180002029`: `ReplaceObject`

## pseudocode

```c
__int64 __fastcall ReplaceObject(
        LPCWSTR lpSubKey,
        int a2,
        int a3,
        int a4,
        __int64 a5,
        LPCWSTR StringSecurityDescriptor)
{
  unsigned int v10; // eax
  unsigned int v11; // ebx
  unsigned int v12; // eax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  unsigned int valid; // eax
  __int64 v16; // r9
  unsigned int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rax
  __int64 v20; // rcx
  int v22; // [rsp+24h] [rbp-34h] BYREF
  __int64 v23; // [rsp+28h] [rbp-30h] BYREF

  v22 = 0;
  v23 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, WPP_fd6184a389643c6486807174a58ed414_Traceguids);
  v10 = AcquireLockSecurityObject(&v22);
  v11 = v10;
  if ( v10 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_L(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, WPP_fd6184a389643c6486807174a58ed414_Traceguids, v10);
    goto LABEL_33;
  }
  if ( !lpSubKey
    || !a5
    || !*(_QWORD *)a5
    || (v12 = *(_DWORD *)(a5 + 8), v12 >= 0x14)
    || !*(_QWORD *)(*(_QWORD *)&g_pSecurity + 8LL * v12 + 120) )
  {
    v11 = 87;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_33;
    v14 = 100;
    goto LABEL_31;
  }
  if ( !a4 && a2 != *(_DWORD *)(*(_QWORD *)&g_pSecurity + 4LL * v12 + 280) )
  {
    v11 = 5;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_33;
    v14 = 101;
LABEL_31:
    v16 = v11;
    goto LABEL_32;
  }
  valid = ConvertSDDLToValidSecurityDescriptor(StringSecurityDescriptor);
  v11 = valid;
  if ( valid )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_33;
    v14 = 102;
    v16 = valid;
LABEL_32:
    WPP_SF_L(v13[2], v14, WPP_fd6184a389643c6486807174a58ed414_Traceguids, v16);
    goto LABEL_33;
  }
  if ( a4
    || (v17 = WriteSecurityDescriptorToRegistry(lpSubKey, *(LPCWSTR *)a5, 0, (const BYTE *)StringSecurityDescriptor),
        (v11 = v17) == 0) )
  {
    FreeMemory(*(_QWORD *)&g_pSecurity + 120LL + 8LL * *(unsigned int *)(a5 + 8), "ReplaceObject", 986);
    v18 = *(_QWORD *)&g_pSecurity;
    *(_DWORD *)(*(_QWORD *)&g_pSecurity + 4LL * *(unsigned int *)(a5 + 8) + 280) = a3;
    v19 = v23;
    v20 = *(unsigned int *)(a5 + 8);
    v23 = 0;
    *(_QWORD *)(v18 + 8 * v20 + 120) = v19;
    goto LABEL_33;
  }
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v14 = 103;
    v16 = v17;
    goto LABEL_32;
  }
LABEL_33:
  ReleaseLockSecurityObject(&v22);
  if ( v23 )
    FreeMemory(&v23, "ReplaceObject", 996);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_L(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, WPP_fd6184a389643c6486807174a58ed414_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x180001dc0  mov     rax, rsp
0x180001dc3  push    rbx
0x180001dc4  sub     rsp, 50h
0x180001dc8  mov     [rax+8], rbp
0x180001dcc  mov     rbp, rcx
0x180001dcf  mov     [rax+18h], rdi
0x180001dd3  mov     edi, r9d
0x180001dd6  mov     [rax-10h], r12
0x180001dda  xor     r12d, r12d
0x180001ddd  mov     [rax-18h], r13
0x180001de1  mov     [rax-20h], r14
0x180001de5  mov     r14d, edx
0x180001de8  mov     [rax-28h], r15
0x180001dec  mov     r15d, r8d
0x180001def  mov     [rax-34h], r12d
0x180001df3  mov     [rax-30h], r12
0x180001df7  mov     [rax-38h], r12d
0x180001dfb  mov     rcx, cs:WPP_GLOBAL_Control
0x180001e02  lea     r13, WPP_GLOBAL_Control
0x180001e09  cmp     rcx, r13
0x180001e0c  jz      short loc_180001E29
0x180001e0e  test    byte ptr [rcx+1Ch], 8
0x180001e12  jz      short loc_180001E29
0x180001e14  mov     rcx, [rcx+10h]
0x180001e18  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180001e1f  mov     edx, 62h ; 'b'
0x180001e24  call    WPP_SF_
0x180001e29  lea     rcx, [rsp+58h+var_34]
0x180001e2e  call    AcquireLockSecurityObject
0x180001e33  mov     ebx, eax
0x180001e35  test    eax, eax
0x180001e37  jz      short loc_180001E70
0x180001e39  mov     rcx, cs:WPP_GLOBAL_Control
0x180001e40  cmp     rcx, r13
0x180001e43  jz      loc_180001FF8
0x180001e49  test    byte ptr [rcx+1Ch], 4
0x180001e4d  jz      loc_180001FF8
0x180001e53  mov     rcx, [rcx+10h]
0x180001e57  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180001e5e  mov     edx, 63h ; 'c'
0x180001e63  mov     r9d, eax
0x180001e66  call    WPP_SF_L
0x180001e6b  jmp     loc_180001FF8
0x180001e70  mov     [rsp+58h+arg_8], rsi
0x180001e75  test    rbp, rbp
0x180001e78  jz      loc_180001FC4
0x180001e7e  mov     rsi, [rsp+58h+arg_20]
0x180001e86  test    rsi, rsi
0x180001e89  jz      loc_180001FC4
0x180001e8f  cmp     [rsi], r12
0x180001e92  jz      loc_180001FC4
0x180001e98  mov     eax, [rsi+8]
0x180001e9b  cmp     eax, 14h
0x180001e9e  jnb     loc_180001FC4
0x180001ea4  mov     ecx, eax
0x180001ea6  mov     rax, cs:g_pSecurity
0x180001ead  cmp     [rax+rcx*8+78h], r12
0x180001eb2  jz      loc_180001FC4
0x180001eb8  test    edi, edi
0x180001eba  jnz     short loc_180001EEF
0x180001ebc  cmp     r14d, [rax+rcx*4+118h]
0x180001ec4  jz      short loc_180001EEF
0x180001ec6  mov     ebx, 5
0x180001ecb  mov     rcx, cs:WPP_GLOBAL_Control
0x180001ed2  cmp     rcx, r13
0x180001ed5  jz      loc_180001FF3
0x180001edb  test    byte ptr [rcx+1Ch], 4
0x180001edf  jz      loc_180001FF3
0x180001ee5  mov     edx, 65h ; 'e'
0x180001eea  jmp     loc_180001FE0
0x180001eef  mov     r14, [rsp+58h+StringSecurityDescriptor]
0x180001ef7  lea     r9, [rsp+58h+var_30]
0x180001efc  mov     edx, [rsi+0Ch]
0x180001eff  lea     r8, [rsp+58h+var_38]
0x180001f04  mov     rcx, r14; StringSecurityDescriptor
0x180001f07  call    ConvertSDDLToValidSecurityDescriptor
0x180001f0c  mov     ebx, eax
0x180001f0e  test    eax, eax
0x180001f10  jz      short loc_180001F39
0x180001f12  mov     rcx, cs:WPP_GLOBAL_Control
0x180001f19  cmp     rcx, r13
0x180001f1c  jz      loc_180001FF3
0x180001f22  test    byte ptr [rcx+1Ch], 4
0x180001f26  jz      loc_180001FF3
0x180001f2c  mov     edx, 66h ; 'f'
0x180001f31  mov     r9d, eax
0x180001f34  jmp     loc_180001FE3
0x180001f39  test    edi, edi
0x180001f3b  jnz     short loc_180001F7A
0x180001f3d  mov     r8d, [rsp+58h+var_38]
0x180001f42  mov     r9, r14
0x180001f45  mov     rdx, [rsi]; lpValueName
0x180001f48  mov     rcx, rbp; lpSubKey
0x180001f4b  call    WriteSecurityDescriptorToRegistry
0x180001f50  mov     ebx, eax
0x180001f52  test    eax, eax
0x180001f54  jz      short loc_180001F7A
0x180001f56  mov     rcx, cs:WPP_GLOBAL_Control
0x180001f5d  cmp     rcx, r13
0x180001f60  jz      loc_180001FF3
0x180001f66  test    byte ptr [rcx+1Ch], 4
0x180001f6a  jz      loc_180001FF3
0x180001f70  mov     edx, 67h ; 'g'
0x180001f75  mov     r9d, eax
0x180001f78  jmp     short loc_180001FE3
0x180001f7a  mov     rax, cs:g_pSecurity
0x180001f81  lea     rdx, aReplaceobject_0; "ReplaceObject"
0x180001f88  mov     ecx, [rsi+8]
0x180001f8b  add     rax, 78h ; 'x'
0x180001f8f  mov     r8d, 3DAh
0x180001f95  lea     rcx, [rax+rcx*8]
0x180001f99  call    FreeMemory
0x180001f9e  mov     eax, [rsi+8]
0x180001fa1  mov     rdx, cs:g_pSecurity
0x180001fa8  mov     [rdx+rax*4+118h], r15d
0x180001fb0  mov     rax, [rsp+58h+var_30]
0x180001fb5  mov     ecx, [rsi+8]
0x180001fb8  mov     [rsp+58h+var_30], r12
0x180001fbd  mov     [rdx+rcx*8+78h], rax
0x180001fc2  jmp     short loc_180001FF3
0x180001fc4  mov     ebx, 57h ; 'W'
0x180001fc9  mov     rcx, cs:WPP_GLOBAL_Control
0x180001fd0  cmp     rcx, r13
0x180001fd3  jz      short loc_180001FF3
0x180001fd5  test    byte ptr [rcx+1Ch], 4
0x180001fd9  jz      short loc_180001FF3
0x180001fdb  mov     edx, 64h ; 'd'
0x180001fe0  mov     r9d, ebx
0x180001fe3  mov     rcx, [rcx+10h]
0x180001fe7  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180001fee  call    WPP_SF_L
0x180001ff3  mov     rsi, [rsp+58h+arg_8]
0x180001ff8  lea     rcx, [rsp+58h+var_34]
0x180001ffd  call    ReleaseLockSecurityObject
0x180002002  cmp     [rsp+58h+var_30], 0
0x180002008  mov     r15, [rsp+58h+var_28]
0x18000200d  mov     r14, [rsp+58h+var_20]
0x180002012  mov     r12, [rsp+58h+var_10]
0x180002017  mov     rdi, [rsp+58h+arg_10]
0x18000201c  mov     rbp, [rsp+58h+arg_0]
0x180002021  jz      short loc_18000203A
0x180002023  mov     r8d, 3E4h
0x180002029  lea     rdx, aReplaceobject_0; "ReplaceObject"
0x180002030  lea     rcx, [rsp+58h+var_30]
0x180002035  call    FreeMemory
0x18000203a  mov     rcx, cs:WPP_GLOBAL_Control
0x180002041  cmp     rcx, r13
0x180002044  mov     r13, [rsp+58h+var_18]
0x180002049  jz      short loc_180002069
0x18000204b  test    byte ptr [rcx+1Ch], 8
0x18000204f  jz      short loc_180002069
0x180002051  mov     rcx, [rcx+10h]
0x180002055  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x18000205c  mov     edx, 68h ; 'h'
0x180002061  mov     r9d, ebx
0x180002064  call    WPP_SF_L
0x180002069  mov     eax, ebx
0x18000206b  add     rsp, 50h
0x18000206f  pop     rbx
0x180002070  retn
```
