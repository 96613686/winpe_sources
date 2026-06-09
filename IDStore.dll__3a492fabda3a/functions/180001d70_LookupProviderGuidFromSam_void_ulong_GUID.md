# LookupProviderGuidFromSam(void *,ulong,_GUID *)

- ea: `0x180001d70`
- end: `0x180001f94`
- name: `?LookupProviderGuidFromSam@@YAJPEAXKPEAU_GUID@@@Z`
- size: `548`
- prototype: `__int64 __fastcall(void *, unsigned int, struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800037a0`

## callees

- `0x180001d70`
- `0x1800144b4`
- `0x1800144f4`
- `0x1800191ac`
- `0x180019210`

## import_xrefs

- `SAMLIB!SamQueryInformationUser` at `0x180001de6`
- `SAMLIB!SamQueryInformationUser` at `0x180001de6`
- `SAMLIB!SamFreeMemory` at `0x180001e8c`
- `SAMLIB!SamFreeMemory` at `0x180001e8c`
- `SAMLIB!SamCloseHandle` at `0x180001e72`
- `SAMLIB!SamCloseHandle` at `0x180001e72`
- `SAMLIB!SamOpenUser` at `0x180001dc7`
- `SAMLIB!SamOpenUser` at `0x180001dc7`

## pseudocode

```c
__int64 __fastcall LookupProviderGuidFromSam(void *a1, unsigned int a2, struct _GUID *a3)
{
  int v6; // eax
  int v7; // edx
  __int64 v8; // r8
  int v9; // ebx
  int InformationUser; // eax
  __int64 v11; // rcx
  CIdentityProfileHandler *v12; // rcx
  int v13; // ebx
  _QWORD v15[5]; // [rsp+30h] [rbp-28h] BYREF
  __int64 v16; // [rsp+78h] [rbp+20h] BYREF

  v16 = 0;
  v15[0] = 0;
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, a3, "LookupProviderGuidFromSam");
  }
  v6 = SamOpenUser(a1, 0x2000000, a2, &v16);
  v9 = v6;
  if ( v6 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, WPP_08388c1448a138cd62261a2bdb1dad4c_Traceguids, a2, v6);
      v12 = WPP_GLOBAL_Control;
    }
LABEL_25:
    v13 = v9 | 0x10000000;
    goto LABEL_15;
  }
  InformationUser = SamQueryInformationUser(v16, 28, v15);
  v9 = InformationUser;
  if ( InformationUser < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        76,
        WPP_08388c1448a138cd62261a2bdb1dad4c_Traceguids,
        (unsigned int)InformationUser);
      v13 = v9 | 0x10000000;
      goto LABEL_14;
    }
    goto LABEL_25;
  }
  if ( (*(_DWORD *)v15[0] & 0x40000) != 0 )
  {
    v11 = *(_QWORD *)(v15[0] + 96LL) - *(_QWORD *)&GUID_NULL.Data1;
    if ( !v11 )
      v11 = *(_QWORD *)(v15[0] + 104LL) - *(_QWORD *)GUID_NULL.Data4;
    if ( v11 )
    {
      v13 = 0;
      *a3 = *(struct _GUID *)(v15[0] + 96LL);
      goto LABEL_14;
    }
  }
  v12 = WPP_GLOBAL_Control;
  v13 = -2147024809;
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, WPP_08388c1448a138cd62261a2bdb1dad4c_Traceguids, 2147942487LL);
LABEL_14:
    v12 = WPP_GLOBAL_Control;
  }
LABEL_15:
  if ( v16 )
  {
    SamCloseHandle(v16);
    v12 = WPP_GLOBAL_Control;
  }
  if ( v15[0] )
  {
    SamFreeMemory(v15[0]);
    v12 = WPP_GLOBAL_Control;
  }
  if ( v13 < 0 )
  {
    if ( v12 == (CIdentityProfileHandler *)&WPP_GLOBAL_Control )
      return (unsigned int)v13;
    if ( (*((_BYTE *)v12 + 28) & 4) != 0 )
    {
      WPP_SF_sL(*((_QWORD *)v12 + 2), v7, v8, (unsigned int)"LookupProviderGuidFromSam", v13);
      v12 = WPP_GLOBAL_Control;
    }
  }
  if ( v12 != (CIdentityProfileHandler *)&WPP_GLOBAL_Control && (*((_DWORD *)v12 + 7) & 0x400) != 0 )
    WPP_SF_s(*((_QWORD *)v12 + 2), 12, v8, "LookupProviderGuidFromSam");
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180001d70  mov     [rsp+arg_0], rbx
0x180001d75  mov     [rsp+arg_8], rbp
0x180001d7a  push    rsi
0x180001d7b  push    rdi
0x180001d7c  push    r14
0x180001d7e  sub     rsp, 40h
0x180001d82  xor     r14d, r14d
0x180001d85  mov     rsi, r8
0x180001d88  mov     [rsp+58h+arg_18], r14
0x180001d8d  mov     edi, edx
0x180001d8f  mov     [rsp+58h+var_28], r14
0x180001d94  mov     rbx, rcx
0x180001d97  mov     rcx, cs:WPP_GLOBAL_Control
0x180001d9e  lea     rbp, WPP_GLOBAL_Control
0x180001da5  cmp     rcx, rbp
0x180001da8  jz      short loc_180001DB7
0x180001daa  test    dword ptr [rcx+1Ch], 400h
0x180001db1  jnz     loc_180001EFE
0x180001db7  lea     r9, [rsp+58h+arg_18]
0x180001dbc  mov     r8d, edi
0x180001dbf  mov     edx, 2000000h
0x180001dc4  mov     rcx, rbx
0x180001dc7  call    cs:__imp_SamOpenUser
0x180001dcd  mov     ebx, eax
0x180001dcf  test    eax, eax
0x180001dd1  js      loc_180001EC4
0x180001dd7  mov     rcx, [rsp+58h+arg_18]
0x180001ddc  lea     r8, [rsp+58h+var_28]
0x180001de1  mov     edx, 1Ch
0x180001de6  call    cs:__imp_SamQueryInformationUser
0x180001dec  mov     ebx, eax
0x180001dee  test    eax, eax
0x180001df0  js      loc_180001F43
0x180001df6  mov     rax, [rsp+58h+var_28]
0x180001dfb  test    dword ptr [rax], 40000h
0x180001e01  jz      short loc_180001E20
0x180001e03  mov     rcx, [rax+60h]
0x180001e07  sub     rcx, qword ptr cs:GUID_NULL.Data1
0x180001e0e  jnz     short loc_180001E1B
0x180001e10  mov     rcx, [rax+68h]
0x180001e14  sub     rcx, qword ptr cs:GUID_NULL.Data4
0x180001e1b  test    rcx, rcx
0x180001e1e  jnz     short loc_180001E54
0x180001e20  mov     rcx, cs:WPP_GLOBAL_Control
0x180001e27  mov     ebx, 80070057h
0x180001e2c  cmp     rcx, rbp
0x180001e2f  jz      short loc_180001E65
0x180001e31  test    byte ptr [rcx+1Ch], 4
0x180001e35  jz      short loc_180001E65
0x180001e37  mov     rcx, [rcx+10h]
0x180001e3b  lea     r8, WPP_08388c1448a138cd62261a2bdb1dad4c_Traceguids
0x180001e42  mov     edx, 4Dh ; 'M'
0x180001e47  mov     r9d, 80070057h
0x180001e4d  call    WPP_SF_d
0x180001e52  jmp     short loc_180001E5E
0x180001e54  movups  xmm0, xmmword ptr [rax+60h]
0x180001e58  mov     ebx, r14d
0x180001e5b  movups  xmmword ptr [rsi], xmm0
0x180001e5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180001e65  mov     rax, [rsp+58h+arg_18]
0x180001e6a  test    rax, rax
0x180001e6d  jz      short loc_180001E7F
0x180001e6f  mov     rcx, rax
0x180001e72  call    cs:__imp_SamCloseHandle
0x180001e78  mov     rcx, cs:WPP_GLOBAL_Control
0x180001e7f  mov     rax, [rsp+58h+var_28]
0x180001e84  test    rax, rax
0x180001e87  jz      short loc_180001E99
0x180001e89  mov     rcx, rax
0x180001e8c  call    cs:__imp_SamFreeMemory
0x180001e92  mov     rcx, cs:WPP_GLOBAL_Control
0x180001e99  test    ebx, ebx
0x180001e9b  js      short loc_180001ED6
0x180001e9d  cmp     rcx, rbp
0x180001ea0  jz      short loc_180001EAF
0x180001ea2  test    dword ptr [rcx+1Ch], 400h
0x180001ea9  jnz     loc_180001F7A
0x180001eaf  mov     rbp, [rsp+58h+arg_8]
0x180001eb4  mov     eax, ebx
0x180001eb6  mov     rbx, [rsp+58h+arg_0]
0x180001ebb  add     rsp, 40h
0x180001ebf  pop     r14
0x180001ec1  pop     rdi
0x180001ec2  pop     rsi
0x180001ec3  retn
0x180001ec4  mov     rcx, cs:WPP_GLOBAL_Control
0x180001ecb  cmp     rcx, rbp
0x180001ece  jnz     short loc_180001F18
0x180001ed0  bts     ebx, 1Ch
0x180001ed4  jmp     short loc_180001E65
0x180001ed6  cmp     rcx, rbp
0x180001ed9  jz      short loc_180001EAF
0x180001edb  test    byte ptr [rcx+1Ch], 4
0x180001edf  jz      short loc_180001E9D
0x180001ee1  mov     rcx, [rcx+10h]
0x180001ee5  lea     r9, aLookupprovider; "LookupProviderGuidFromSam"
0x180001eec  mov     [rsp+58h+var_38], ebx
0x180001ef0  call    WPP_SF_sL
0x180001ef5  mov     rcx, cs:WPP_GLOBAL_Control
0x180001efc  jmp     short loc_180001E9D
0x180001efe  mov     rcx, [rcx+10h]
0x180001f02  lea     r9, aLookupprovider; "LookupProviderGuidFromSam"
0x180001f09  mov     edx, 0Ah
0x180001f0e  call    WPP_SF_s
0x180001f13  jmp     loc_180001DB7
0x180001f18  test    byte ptr [rcx+1Ch], 4
0x180001f1c  jz      short loc_180001ED0
0x180001f1e  mov     rcx, [rcx+10h]
0x180001f22  lea     r8, WPP_08388c1448a138cd62261a2bdb1dad4c_Traceguids
0x180001f29  mov     edx, 4Bh ; 'K'
0x180001f2e  mov     [rsp+58h+var_38], ebx
0x180001f32  mov     r9d, edi
0x180001f35  call    WPP_SF_DD
0x180001f3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180001f41  jmp     short loc_180001ED0
0x180001f43  mov     rcx, cs:WPP_GLOBAL_Control
0x180001f4a  cmp     rcx, rbp
0x180001f4d  jz      short loc_180001ED0
0x180001f4f  test    byte ptr [rcx+1Ch], 4
0x180001f53  jz      loc_180001ED0
0x180001f59  mov     rcx, [rcx+10h]
0x180001f5d  lea     r8, WPP_08388c1448a138cd62261a2bdb1dad4c_Traceguids
0x180001f64  mov     edx, 4Ch ; 'L'
0x180001f69  mov     r9d, ebx
0x180001f6c  call    WPP_SF_d
0x180001f71  bts     ebx, 1Ch
0x180001f75  jmp     loc_180001E5E
0x180001f7a  mov     rcx, [rcx+10h]
0x180001f7e  lea     r9, aLookupprovider; "LookupProviderGuidFromSam"
0x180001f85  mov     edx, 0Ch
0x180001f8a  call    WPP_SF_s
0x180001f8f  jmp     loc_180001EAF
```
