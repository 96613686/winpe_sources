# ShieldProvider::AccountProtectionShield::RegSetValueDword(ushort const *,int)

- ea: `0x1800c9f14`
- end: `0x1800ca0ca`
- name: `?RegSetValueDword@AccountProtectionShield@ShieldProvider@@AEAAJPEBGH@Z`
- size: `438`
- prototype: `int(ShieldProvider::AccountProtectionShield *__hidden this, const unsigned __int16 *, int)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800c56c0`
- `0x1800c5760`
- `0x1800c58a0`
- `0x1800c7630`
- `0x1800caab0`

## callees

- `0x18000d7fc`
- `0x1800c9f14`
- `0x1800dd3e8`
- `0x1800de1bc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c9f94`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ca010`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ca085`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ca094`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ca0a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ca0b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c9f94`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ca010`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ca085`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ca094`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ca0a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ca0b5`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800c9f3f`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800c9f3f`

## pseudocode

```c
__int64 __fastcall ShieldProvider::AccountProtectionShield::RegSetValueDword(
        ShieldProvider::AccountProtectionShield *this,
        const unsigned __int16 *a2,
        int a3)
{
  LSTATUS v5; // eax
  int Key; // ebx
  HKEY v8; // rbx
  int v9; // edi
  struct _SECURITY_ATTRIBUTES *v10; // [rsp+28h] [rbp-18h]
  HKEY hKey[2]; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int64 v12; // [rsp+60h] [rbp+20h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp+38h] BYREF

  v12 = (unsigned __int64)this;
  phkResult = 0;
  v5 = RegOpenCurrentUser(0x20006u, &phkResult);
  Key = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      Key = (unsigned __int16)v5 | 0x80070000;
    if ( Key < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          54,
          WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids,
          (unsigned int)Key);
LABEL_8:
      if ( phkResult )
        RegCloseKey(phkResult);
      return (unsigned int)Key;
    }
  }
  hKey[0] = 0;
  Key = CommonUtil::UtilRegCreateKey(
          (CommonUtil *)hKey,
          (HKEY *)phkResult,
          (const WCHAR *)&stru_180100C70,
          (const unsigned __int16 *)0x20006,
          0,
          v10);
  if ( Key < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        55,
        WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids,
        (unsigned int)Key);
    if ( hKey[0] )
      RegCloseKey(hKey[0]);
    goto LABEL_8;
  }
  v8 = hKey[0];
  LODWORD(v12) = a3 != 0;
  v9 = CommonUtil::UtilRegSetValueInternal((CommonUtil *)hKey[0], a2, (const unsigned __int16 *)4, 4, (BYTE *)&v12);
  if ( v9 >= 0 )
  {
    if ( v8 )
      RegCloseKey(v8);
    if ( phkResult )
      RegCloseKey(phkResult);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        56,
        WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids,
        (unsigned int)v9);
    if ( v8 )
      RegCloseKey(v8);
    if ( phkResult )
      RegCloseKey(phkResult);
    return (unsigned int)v9;
  }
}

```

## disassembly

```asm
0x1800c9f14  mov     [rsp-18h+arg_8], rbx
0x1800c9f19  mov     [rsp-18h+arg_0], rcx
0x1800c9f1e  push    rbp
0x1800c9f1f  push    rsi
0x1800c9f20  push    rdi
0x1800c9f21  mov     rbp, rsp
0x1800c9f24  sub     rsp, 40h
0x1800c9f28  mov     rsi, rdx
0x1800c9f2b  mov     [rbp+phkResult], 0
0x1800c9f33  lea     rdx, [rbp+phkResult]; phkResult
0x1800c9f37  mov     ecx, 20006h; samDesired
0x1800c9f3c  mov     edi, r8d
0x1800c9f3f  call    cs:__imp_RegOpenCurrentUser
0x1800c9f45  mov     ebx, eax
0x1800c9f47  test    eax, eax
0x1800c9f49  jz      short loc_1800C9FA1
0x1800c9f4b  jle     short loc_1800C9F56
0x1800c9f4d  movzx   ebx, ax
0x1800c9f50  or      ebx, 80070000h
0x1800c9f56  test    ebx, ebx
0x1800c9f58  jns     short loc_1800C9FA1
0x1800c9f5a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c9f61  lea     rax, WPP_GLOBAL_Control
0x1800c9f68  cmp     rcx, rax
0x1800c9f6b  jz      short loc_1800C9F8B
0x1800c9f6d  test    byte ptr [rcx+1Ch], 1
0x1800c9f71  jz      short loc_1800C9F8B
0x1800c9f73  mov     rcx, [rcx+10h]
0x1800c9f77  lea     r8, WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids
0x1800c9f7e  mov     edx, 36h ; '6'
0x1800c9f83  mov     r9d, ebx
0x1800c9f86  call    WPP_SF_d
0x1800c9f8b  mov     rcx, [rbp+phkResult]; hKey
0x1800c9f8f  test    rcx, rcx
0x1800c9f92  jz      short loc_1800C9F9A
0x1800c9f94  call    cs:__imp_RegCloseKey
0x1800c9f9a  mov     eax, ebx
0x1800c9f9c  jmp     loc_1800CA0BD
0x1800c9fa1  mov     rdx, [rbp+phkResult]; HKEY *
0x1800c9fa5  lea     r8, stru_180100C70; HKEY
0x1800c9fac  mov     r9d, 20006h; unsigned __int16 *
0x1800c9fb2  mov     [rbp+hKey], 0
0x1800c9fba  lea     rcx, [rbp+hKey]; this
0x1800c9fbe  mov     qword ptr [rsp+40h+var_20], 0; unsigned int
0x1800c9fc7  call    ?UtilRegCreateKey@CommonUtil@@YAJPEAPEAUHKEY__@@PEAU2@PEBGKPEAU_SECURITY_ATTRIBUTES@@K@Z; CommonUtil::UtilRegCreateKey(HKEY__ * *,HKEY__ *,ushort const *,ulong,_SECURITY_ATTRIBUTES *,ulong)
0x1800c9fcc  mov     ebx, eax
0x1800c9fce  test    eax, eax
0x1800c9fd0  jns     short loc_1800CA01B
0x1800c9fd2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c9fd9  lea     rax, WPP_GLOBAL_Control
0x1800c9fe0  cmp     rcx, rax
0x1800c9fe3  jz      short loc_1800CA003
0x1800c9fe5  test    byte ptr [rcx+1Ch], 1
0x1800c9fe9  jz      short loc_1800CA003
0x1800c9feb  mov     rcx, [rcx+10h]
0x1800c9fef  lea     r8, WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids
0x1800c9ff6  mov     edx, 37h ; '7'
0x1800c9ffb  mov     r9d, ebx
0x1800c9ffe  call    WPP_SF_d
0x1800ca003  mov     rcx, [rbp+hKey]; hKey
0x1800ca007  test    rcx, rcx
0x1800ca00a  jz      loc_1800C9F8B
0x1800ca010  call    cs:__imp_RegCloseKey
0x1800ca016  jmp     loc_1800C9F8B
0x1800ca01b  mov     rbx, [rbp+hKey]
0x1800ca01f  xor     eax, eax
0x1800ca021  mov     r8d, 4; unsigned __int16 *
0x1800ca027  test    edi, edi
0x1800ca029  mov     r9d, r8d; unsigned int
0x1800ca02c  mov     rdx, rsi; HKEY
0x1800ca02f  setnz   al
0x1800ca032  mov     rcx, rbx; this
0x1800ca035  mov     dword ptr [rbp+arg_0], eax
0x1800ca038  lea     rax, [rbp+arg_0]
0x1800ca03c  mov     qword ptr [rsp+40h+var_20], rax; unsigned __int64
0x1800ca041  call    ?UtilRegSetValueInternal@CommonUtil@@YAJPEAUHKEY__@@PEBGK_KPEBX@Z; CommonUtil::UtilRegSetValueInternal(HKEY__ *,ushort const *,ulong,unsigned __int64,void const *)
0x1800ca046  mov     edi, eax
0x1800ca048  test    eax, eax
0x1800ca04a  jns     short loc_1800CA09E
0x1800ca04c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ca053  lea     rax, WPP_GLOBAL_Control
0x1800ca05a  cmp     rcx, rax
0x1800ca05d  jz      short loc_1800CA07D
0x1800ca05f  test    byte ptr [rcx+1Ch], 1
0x1800ca063  jz      short loc_1800CA07D
0x1800ca065  mov     rcx, [rcx+10h]
0x1800ca069  lea     r8, WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids
0x1800ca070  mov     edx, 38h ; '8'
0x1800ca075  mov     r9d, edi
0x1800ca078  call    WPP_SF_d
0x1800ca07d  test    rbx, rbx
0x1800ca080  jz      short loc_1800CA08B
0x1800ca082  mov     rcx, rbx; hKey
0x1800ca085  call    cs:__imp_RegCloseKey
0x1800ca08b  mov     rcx, [rbp+phkResult]; hKey
0x1800ca08f  test    rcx, rcx
0x1800ca092  jz      short loc_1800CA09A
0x1800ca094  call    cs:__imp_RegCloseKey
0x1800ca09a  mov     eax, edi
0x1800ca09c  jmp     short loc_1800CA0BD
0x1800ca09e  test    rbx, rbx
0x1800ca0a1  jz      short loc_1800CA0AC
0x1800ca0a3  mov     rcx, rbx; hKey
0x1800ca0a6  call    cs:__imp_RegCloseKey
0x1800ca0ac  mov     rcx, [rbp+phkResult]; hKey
0x1800ca0b0  test    rcx, rcx
0x1800ca0b3  jz      short loc_1800CA0BB
0x1800ca0b5  call    cs:__imp_RegCloseKey
0x1800ca0bb  xor     eax, eax
0x1800ca0bd  mov     rbx, [rsp+40h+arg_8]
0x1800ca0c2  add     rsp, 40h
0x1800ca0c6  pop     rdi
0x1800ca0c7  pop     rsi
0x1800ca0c8  pop     rbp
0x1800ca0c9  retn
```
