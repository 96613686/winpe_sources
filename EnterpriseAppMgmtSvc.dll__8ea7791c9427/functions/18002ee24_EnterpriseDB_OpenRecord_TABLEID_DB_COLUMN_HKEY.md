# EnterpriseDB::OpenRecord(TABLEID,DB_COLUMN &,HKEY__ * *)

- ea: `0x18002ee24`
- end: `0x18002efa4`
- name: `?OpenRecord@EnterpriseDB@@AEAAJW4TABLEID@@AEAUDB_COLUMN@@PEAPEAUHKEY__@@@Z`
- size: `384`
- prototype: `int __high(enum TABLEID, struct DB_COLUMN *, HKEY *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b878`
- `0x18002f20c`

## callees

- `0x180006858`
- `0x18002ee24`
- `0x180066db2`
- `0x180066df0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002eee2`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002eee2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ef7e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ef7e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ee74`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ee74`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ef17`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ef17`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EnterpriseDB::OpenRecord(__int64 a1, int a2, __int64 a3, HKEY *a4)
{
  __int64 v6; // rbx
  __int64 v8; // rcx
  unsigned int v9; // ebx
  LPCWSTR *v10; // rax
  LSTATUS v11; // eax
  __int64 v12; // r9
  __int64 *v13; // rdx
  GUID rguid; // [rsp+40h] [rbp-98h] BYREF
  OLECHAR sz[40]; // [rsp+50h] [rbp-88h] BYREF

  v6 = a2;
  memset_0(sz, 0, sizeof(sz));
  rguid = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
  if ( !*(_DWORD *)a1 )
  {
LABEL_2:
    v9 = -2147467259;
    goto LABEL_21;
  }
  if ( !a4
    || (unsigned int)v6 > 1
    || (v8 = 3 * v6, (v10 = &(&g_TableInfo)[3 * v6]) == 0)
    || *(_WORD *)a3 != *((_WORD *)v10 + 6) )
  {
    v9 = -2147024809;
    goto LABEL_21;
  }
  rguid = *(GUID *)*(_QWORD *)(a3 + 8);
  if ( !StringFromGUID2(&rguid, sz, 40) )
    goto LABEL_2;
  v8 = (_DWORD)v6 ? *(_QWORD *)(a1 + 16) : *(_QWORD *)(a1 + 8);
  if ( !v8 )
    goto LABEL_2;
  v11 = RegOpenKeyExW((HKEY)v8, sz, 0, 0xF003Fu, a4);
  v9 = v11;
  if ( !v11 )
  {
    v9 = 0;
    goto LABEL_24;
  }
  if ( v11 > 0 )
    v9 = (unsigned __int16)v11 | 0x80070000;
  if ( (v9 & 0x80000000) != 0 )
  {
    if ( v9 == -2147024894 )
    {
      if ( (Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits & 0x200) != 0 )
      {
        v12 = 2147942402LL;
        v13 = EnterpriseAppDBWarning;
LABEL_23:
        McTemplateU0zq_EventWriteTransfer(v8, v13, L"Record does not exist", v12);
        goto LABEL_24;
      }
      goto LABEL_24;
    }
LABEL_21:
    if ( (Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits & 0x100) != 0 )
    {
      v12 = v9;
      v13 = EnterpriseAppDBError;
      goto LABEL_23;
    }
  }
LABEL_24:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
  return v9;
}

```

## disassembly

```asm
0x18002ee24  push    rbx
0x18002ee26  push    rbp
0x18002ee27  push    rsi
0x18002ee28  push    rdi
0x18002ee29  push    r14
0x18002ee2b  sub     rsp, 0B0h
0x18002ee32  mov     rax, cs:__security_cookie
0x18002ee39  xor     rax, rsp
0x18002ee3c  mov     [rsp+0D8h+var_38], rax
0x18002ee44  mov     rbp, r9
0x18002ee47  mov     rsi, r8
0x18002ee4a  movsxd  rbx, edx
0x18002ee4d  mov     rdi, rcx
0x18002ee50  xor     edx, edx; Val
0x18002ee52  lea     r8d, [rdx+50h]; Size
0x18002ee56  lea     rcx, [rsp+0D8h+sz]; void *
0x18002ee5b  call    memset_0
0x18002ee60  xorps   xmm0, xmm0
0x18002ee63  movups  xmmword ptr [rsp+0D8h+rguid.Data1], xmm0
0x18002ee68  lea     r14, [rdi+18h]
0x18002ee6c  mov     [rsp+0D8h+var_A8], r14
0x18002ee71  mov     rcx, r14; lpCriticalSection
0x18002ee74  call    cs:__imp_EnterCriticalSection
0x18002ee7a  mov     [rsp+0D8h+var_A0], 1
0x18002ee7f  cmp     dword ptr [rdi], 0
0x18002ee82  jnz     short loc_18002EE8E
0x18002ee84  mov     ebx, 80004005h
0x18002ee89  jmp     loc_18002EF5B
0x18002ee8e  test    rbp, rbp
0x18002ee91  jz      loc_18002EF56
0x18002ee97  cmp     ebx, 1
0x18002ee9a  ja      loc_18002EF56
0x18002eea0  lea     rcx, [rbx+rbx*2]
0x18002eea4  lea     rax, ?g_TableInfo@@3PAUTABLE_INFO@@A; TABLE_INFO near * g_TableInfo
0x18002eeab  lea     rax, [rax+rcx*8]
0x18002eeaf  test    rax, rax
0x18002eeb2  jz      loc_18002EF56
0x18002eeb8  movzx   eax, word ptr [rax+0Ch]
0x18002eebc  cmp     [rsi], ax
0x18002eebf  jnz     loc_18002EF56
0x18002eec5  mov     rax, [rsi+8]
0x18002eec9  movups  xmm0, xmmword ptr [rax]
0x18002eecc  movdqu  xmmword ptr [rsp+0D8h+rguid.Data1], xmm0
0x18002eed2  mov     r8d, 28h ; '('; cchMax
0x18002eed8  lea     rdx, [rsp+0D8h+sz]; lpsz
0x18002eedd  lea     rcx, [rsp+0D8h+rguid]; rguid
0x18002eee2  call    cs:__imp_StringFromGUID2
0x18002eee8  test    eax, eax
0x18002eeea  jz      short loc_18002EE84
0x18002eeec  test    ebx, ebx
0x18002eeee  jz      short loc_18002EEFB
0x18002eef0  cmp     ebx, 1
0x18002eef3  jnz     short loc_18002EE84
0x18002eef5  mov     rcx, [rdi+10h]
0x18002eef9  jmp     short loc_18002EEFF
0x18002eefb  mov     rcx, [rdi+8]; hKey
0x18002eeff  test    rcx, rcx
0x18002ef02  jz      short loc_18002EE84
0x18002ef04  mov     [rsp+0D8h+phkResult], rbp; phkResult
0x18002ef09  mov     r9d, 0F003Fh; samDesired
0x18002ef0f  xor     r8d, r8d; ulOptions
0x18002ef12  lea     rdx, [rsp+0D8h+sz]; lpSubKey
0x18002ef17  call    cs:__imp_RegOpenKeyExW
0x18002ef1d  mov     ebx, eax
0x18002ef1f  test    eax, eax
0x18002ef21  jz      short loc_18002EF52
0x18002ef23  jle     short loc_18002EF2E
0x18002ef25  movzx   ebx, ax
0x18002ef28  or      ebx, 80070000h
0x18002ef2e  test    ebx, ebx
0x18002ef30  jns     short loc_18002EF7B
0x18002ef32  cmp     ebx, 80070002h
0x18002ef38  jnz     short loc_18002EF5B
0x18002ef3a  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits+1, 2
0x18002ef41  jz      short loc_18002EF7B
0x18002ef43  mov     r9d, 80070002h
0x18002ef49  lea     rdx, EnterpriseAppDBWarning
0x18002ef50  jmp     short loc_18002EF6E
0x18002ef52  xor     ebx, ebx
0x18002ef54  jmp     short loc_18002EF7B
0x18002ef56  mov     ebx, 80070057h
0x18002ef5b  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits+1, 1
0x18002ef62  jz      short loc_18002EF7B
0x18002ef64  mov     r9d, ebx
0x18002ef67  lea     rdx, EnterpriseAppDBError
0x18002ef6e  lea     r8, aRecordDoesNotE; "Record does not exist"
0x18002ef75  call    McTemplateU0zq_EventWriteTransfer
0x18002ef7a  nop
0x18002ef7b  mov     rcx, r14; lpCriticalSection
0x18002ef7e  call    cs:__imp_LeaveCriticalSection
0x18002ef84  mov     eax, ebx
0x18002ef86  mov     rcx, [rsp+0D8h+var_38]
0x18002ef8e  xor     rcx, rsp; StackCookie
0x18002ef91  call    __security_check_cookie
0x18002ef96  add     rsp, 0B0h
0x18002ef9d  pop     r14
0x18002ef9f  pop     rdi
0x18002efa0  pop     rsi
0x18002efa1  pop     rbp
0x18002efa2  pop     rbx
0x18002efa3  retn
```
