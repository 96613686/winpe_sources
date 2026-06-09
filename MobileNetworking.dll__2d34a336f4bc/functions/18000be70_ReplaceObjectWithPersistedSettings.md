# ReplaceObjectWithPersistedSettings

- ea: `0x18000be70`
- end: `0x18000c041`
- name: `ReplaceObjectWithPersistedSettings`
- size: `465`
- prototype: `__int64 __fastcall(const WCHAR *, int, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180002a40`
- `0x180002b20`
- `0x180002d10`
- `0x180004b80`
- `0x180008ff0`
- `0x180009130`
- `0x18000be70`

## string_xrefs

- `0x18000bf71`: `ReplaceObjectWithPersistedSettings`
- `0x18000bffb`: `ReplaceObjectWithPersistedSettings`

## pseudocode

```c
__int64 __fastcall ReplaceObjectWithPersistedSettings(const WCHAR *a1, int a2, __int64 a3)
{
  unsigned int SecurityDescriptorFromRegistry; // eax
  unsigned int v7; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  __int64 v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rcx
  _QWORD v15[9]; // [rsp+20h] [rbp-48h] BYREF
  int v16; // [rsp+88h] [rbp+20h] BYREF

  v16 = 0;
  v15[0] = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, WPP_fd6184a389643c6486807174a58ed414_Traceguids);
  SecurityDescriptorFromRegistry = AcquireLockSecurityObject(&v16);
  v7 = SecurityDescriptorFromRegistry;
  if ( SecurityDescriptorFromRegistry )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v9 = 106;
LABEL_8:
      v10 = SecurityDescriptorFromRegistry;
LABEL_21:
      WPP_SF_L(v8[2], v9, WPP_fd6184a389643c6486807174a58ed414_Traceguids, v10);
    }
  }
  else if ( a1
         && a3
         && *(_DWORD *)(a3 + 8) < 0x14u
         && *(_QWORD *)(*(_QWORD *)&g_pSecurity + 8LL * *(unsigned int *)(a3 + 8) + 120) )
  {
    SecurityDescriptorFromRegistry = ReadSecurityDescriptorFromRegistry(
                                       a1,
                                       *(const WCHAR **)a3,
                                       *(unsigned int *)(a3 + 12),
                                       (__int64)v15);
    v7 = SecurityDescriptorFromRegistry;
    if ( !SecurityDescriptorFromRegistry )
    {
      FreeMemory(
        *(_QWORD *)&g_pSecurity + 120LL + 8LL * *(unsigned int *)(a3 + 8),
        "ReplaceObjectWithPersistedSettings",
        1024);
      v11 = *(_QWORD *)&g_pSecurity;
      *(_DWORD *)(*(_QWORD *)&g_pSecurity + 4LL * *(unsigned int *)(a3 + 8) + 280) = a2;
      v12 = v15[0];
      v13 = *(unsigned int *)(a3 + 8);
      v15[0] = 0;
      *(_QWORD *)(v11 + 8 * v13 + 120) = v12;
      goto LABEL_22;
    }
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v9 = 108;
      goto LABEL_8;
    }
  }
  else
  {
    v7 = 87;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v9 = 107;
      v10 = 87;
      goto LABEL_21;
    }
  }
LABEL_22:
  ReleaseLockSecurityObject(&v16);
  if ( v15[0] )
    FreeMemory(v15, "ReplaceObjectWithPersistedSettings", 1034);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_L(*((_QWORD *)WPP_GLOBAL_Control + 2), 109, WPP_fd6184a389643c6486807174a58ed414_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x18000be70  mov     rax, rsp
0x18000be73  push    rbx
0x18000be74  push    rbp
0x18000be75  push    rsi
0x18000be76  push    rdi
0x18000be77  push    r12
0x18000be79  push    r15
0x18000be7b  sub     rsp, 38h
0x18000be7f  mov     rdi, r8
0x18000be82  mov     dword ptr [rax+20h], 0
0x18000be89  mov     ebp, edx
0x18000be8b  mov     qword ptr [rax-48h], 0
0x18000be93  mov     rsi, rcx
0x18000be96  mov     rcx, cs:WPP_GLOBAL_Control
0x18000be9d  lea     r15, WPP_GLOBAL_Control
0x18000bea4  lea     r12, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x18000beab  cmp     rcx, r15
0x18000beae  jz      short loc_18000BEC7
0x18000beb0  test    byte ptr [rcx+1Ch], 8
0x18000beb4  jz      short loc_18000BEC7
0x18000beb6  mov     rcx, [rcx+10h]
0x18000beba  mov     edx, 69h ; 'i'
0x18000bebf  mov     r8, r12
0x18000bec2  call    WPP_SF_
0x18000bec7  lea     rcx, [rsp+68h+arg_18]
0x18000becf  call    AcquireLockSecurityObject
0x18000bed4  mov     ebx, eax
0x18000bed6  test    eax, eax
0x18000bed8  jz      short loc_18000BF01
0x18000beda  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bee1  cmp     rcx, r15
0x18000bee4  jz      loc_18000BFE0
0x18000beea  test    byte ptr [rcx+1Ch], 4
0x18000beee  jz      loc_18000BFE0
0x18000bef4  mov     edx, 6Ah ; 'j'
0x18000bef9  mov     r9d, eax
0x18000befc  jmp     loc_18000BFD4
0x18000bf01  test    rsi, rsi
0x18000bf04  jz      loc_18000BFB7
0x18000bf0a  test    rdi, rdi
0x18000bf0d  jz      loc_18000BFB7
0x18000bf13  cmp     dword ptr [rdi+8], 14h
0x18000bf17  jnb     loc_18000BFB7
0x18000bf1d  mov     ecx, [rdi+8]
0x18000bf20  mov     rax, cs:g_pSecurity
0x18000bf27  cmp     qword ptr [rax+rcx*8+78h], 0
0x18000bf2d  jz      loc_18000BFB7
0x18000bf33  mov     r8d, [rdi+0Ch]
0x18000bf37  lea     r9, [rsp+68h+var_48]
0x18000bf3c  mov     rdx, [rdi]
0x18000bf3f  mov     rcx, rsi
0x18000bf42  call    ReadSecurityDescriptorFromRegistry
0x18000bf47  mov     ebx, eax
0x18000bf49  test    eax, eax
0x18000bf4b  jz      short loc_18000BF6A
0x18000bf4d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bf54  cmp     rcx, r15
0x18000bf57  jz      loc_18000BFE0
0x18000bf5d  test    byte ptr [rcx+1Ch], 4
0x18000bf61  jz      short loc_18000BFE0
0x18000bf63  mov     edx, 6Ch ; 'l'
0x18000bf68  jmp     short loc_18000BEF9
0x18000bf6a  mov     rax, cs:g_pSecurity
0x18000bf71  lea     rdx, aReplaceobjectw_0; "ReplaceObjectWithPersistedSettings"
0x18000bf78  mov     ecx, [rdi+8]
0x18000bf7b  add     rax, 78h ; 'x'
0x18000bf7f  mov     r8d, 400h
0x18000bf85  lea     rcx, [rax+rcx*8]
0x18000bf89  call    FreeMemory
0x18000bf8e  mov     eax, [rdi+8]
0x18000bf91  mov     rdx, cs:g_pSecurity
0x18000bf98  mov     [rdx+rax*4+118h], ebp
0x18000bf9f  mov     rax, [rsp+68h+var_48]
0x18000bfa4  mov     ecx, [rdi+8]
0x18000bfa7  mov     [rsp+68h+var_48], 0
0x18000bfb0  mov     [rdx+rcx*8+78h], rax
0x18000bfb5  jmp     short loc_18000BFE0
0x18000bfb7  mov     ebx, 57h ; 'W'
0x18000bfbc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bfc3  cmp     rcx, r15
0x18000bfc6  jz      short loc_18000BFE0
0x18000bfc8  test    byte ptr [rcx+1Ch], 4
0x18000bfcc  jz      short loc_18000BFE0
0x18000bfce  lea     edx, [rbx+14h]
0x18000bfd1  mov     r9d, ebx
0x18000bfd4  mov     rcx, [rcx+10h]
0x18000bfd8  mov     r8, r12
0x18000bfdb  call    WPP_SF_L
0x18000bfe0  lea     rcx, [rsp+68h+arg_18]
0x18000bfe8  call    ReleaseLockSecurityObject
0x18000bfed  cmp     [rsp+68h+var_48], 0
0x18000bff3  jz      short loc_18000C00C
0x18000bff5  mov     r8d, 40Ah
0x18000bffb  lea     rdx, aReplaceobjectw_0; "ReplaceObjectWithPersistedSettings"
0x18000c002  lea     rcx, [rsp+68h+var_48]
0x18000c007  call    FreeMemory
0x18000c00c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c013  cmp     rcx, r15
0x18000c016  jz      short loc_18000C032
0x18000c018  test    byte ptr [rcx+1Ch], 8
0x18000c01c  jz      short loc_18000C032
0x18000c01e  mov     rcx, [rcx+10h]
0x18000c022  mov     edx, 6Dh ; 'm'
0x18000c027  mov     r9d, ebx
0x18000c02a  mov     r8, r12
0x18000c02d  call    WPP_SF_L
0x18000c032  mov     eax, ebx
0x18000c034  add     rsp, 38h
0x18000c038  pop     r15
0x18000c03a  pop     r12
0x18000c03c  pop     rdi
0x18000c03d  pop     rsi
0x18000c03e  pop     rbp
0x18000c03f  pop     rbx
0x18000c040  retn
```
