# EnterpriseDB::OpenRecord(TABLEID,DB_COLUMN &,HKEY__ * *)

- ea: `0x180031820`
- end: `0x1800319bd`
- name: `?OpenRecord@EnterpriseDB@@AEAAJW4TABLEID@@AEAUDB_COLUMN@@PEAPEAUHKEY__@@@Z`
- size: `413`
- prototype: `int __high(enum TABLEID, struct DB_COLUMN *, HKEY *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180031c64`
- `0x180031dc0`

## callees

- `0x180006ac0`
- `0x180031820`
- `0x18006c8d2`
- `0x18006c910`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800318e4`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800318e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031990`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031990`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031870`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031870`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031923`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031923`

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
0x180031820  push    rbx
0x180031822  push    rbp
0x180031823  push    rsi
0x180031824  push    rdi
0x180031825  push    r14
0x180031827  sub     rsp, 0B0h
0x18003182e  mov     rax, cs:__security_cookie
0x180031835  xor     rax, rsp
0x180031838  mov     [rsp+0D8h+var_38], rax
0x180031840  mov     rbp, r9
0x180031843  mov     rsi, r8
0x180031846  movsxd  rbx, edx
0x180031849  mov     rdi, rcx
0x18003184c  xor     edx, edx; Val
0x18003184e  lea     r8d, [rdx+50h]; Size
0x180031852  lea     rcx, [rsp+0D8h+sz]; void *
0x180031857  call    memset_0
0x18003185c  xorps   xmm0, xmm0
0x18003185f  movups  xmmword ptr [rsp+0D8h+rguid.Data1], xmm0
0x180031864  lea     r14, [rdi+18h]
0x180031868  mov     [rsp+0D8h+var_A8], r14
0x18003186d  mov     rcx, r14; lpCriticalSection
0x180031870  call    cs:__imp_EnterCriticalSection
0x180031877  nop     dword ptr [rax+rax+00h]
0x18003187c  mov     [rsp+0D8h+var_A0], 1
0x180031881  cmp     dword ptr [rdi], 0
0x180031884  jnz     short loc_180031890
0x180031886  mov     ebx, 80004005h
0x18003188b  jmp     loc_18003196D
0x180031890  test    rbp, rbp
0x180031893  jz      loc_180031968
0x180031899  cmp     ebx, 1
0x18003189c  ja      loc_180031968
0x1800318a2  lea     rcx, [rbx+rbx*2]
0x1800318a6  lea     rax, ?g_TableInfo@@3PAUTABLE_INFO@@A; TABLE_INFO near * g_TableInfo
0x1800318ad  lea     rax, [rax+rcx*8]
0x1800318b1  test    rax, rax
0x1800318b4  jz      loc_180031968
0x1800318ba  movzx   eax, word ptr [rax+0Ch]
0x1800318be  cmp     [rsi], ax
0x1800318c1  jnz     loc_180031968
0x1800318c7  mov     rax, [rsi+8]
0x1800318cb  movups  xmm0, xmmword ptr [rax]
0x1800318ce  movdqu  xmmword ptr [rsp+0D8h+rguid.Data1], xmm0
0x1800318d4  mov     r8d, 28h ; '('; cchMax
0x1800318da  lea     rdx, [rsp+0D8h+sz]; lpsz
0x1800318df  lea     rcx, [rsp+0D8h+rguid]; rguid
0x1800318e4  call    cs:__imp_StringFromGUID2
0x1800318eb  nop     dword ptr [rax+rax+00h]
0x1800318f0  test    eax, eax
0x1800318f2  jz      short loc_180031886
0x1800318f4  test    ebx, ebx
0x1800318f6  jz      short loc_180031903
0x1800318f8  cmp     ebx, 1
0x1800318fb  jnz     short loc_180031886
0x1800318fd  mov     rcx, [rdi+10h]
0x180031901  jmp     short loc_180031907
0x180031903  mov     rcx, [rdi+8]; hKey
0x180031907  test    rcx, rcx
0x18003190a  jz      loc_180031886
0x180031910  mov     [rsp+0D8h+phkResult], rbp; phkResult
0x180031915  mov     r9d, 0F003Fh; samDesired
0x18003191b  xor     r8d, r8d; ulOptions
0x18003191e  lea     rdx, [rsp+0D8h+sz]; lpSubKey
0x180031923  call    cs:__imp_RegOpenKeyExW
0x18003192a  nop     dword ptr [rax+rax+00h]
0x18003192f  mov     ebx, eax
0x180031931  test    eax, eax
0x180031933  jz      short loc_180031964
0x180031935  jle     short loc_180031940
0x180031937  movzx   ebx, ax
0x18003193a  or      ebx, 80070000h
0x180031940  test    ebx, ebx
0x180031942  jns     short loc_18003198D
0x180031944  cmp     ebx, 80070002h
0x18003194a  jnz     short loc_18003196D
0x18003194c  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits+1, 2
0x180031953  jz      short loc_18003198D
0x180031955  mov     r9d, 80070002h
0x18003195b  lea     rdx, EnterpriseAppDBWarning
0x180031962  jmp     short loc_180031980
0x180031964  xor     ebx, ebx
0x180031966  jmp     short loc_18003198D
0x180031968  mov     ebx, 80070057h
0x18003196d  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits+1, 1
0x180031974  jz      short loc_18003198D
0x180031976  mov     r9d, ebx
0x180031979  lea     rdx, EnterpriseAppDBError
0x180031980  lea     r8, aRecordDoesNotE; "Record does not exist"
0x180031987  call    McTemplateU0zq_EventWriteTransfer
0x18003198c  nop
0x18003198d  mov     rcx, r14; lpCriticalSection
0x180031990  call    cs:__imp_LeaveCriticalSection
0x180031997  nop     dword ptr [rax+rax+00h]
0x18003199c  mov     eax, ebx
0x18003199e  mov     rcx, [rsp+0D8h+var_38]
0x1800319a6  xor     rcx, rsp; StackCookie
0x1800319a9  call    __security_check_cookie
0x1800319ae  add     rsp, 0B0h
0x1800319b5  pop     r14
0x1800319b7  pop     rdi
0x1800319b8  pop     rsi
0x1800319b9  pop     rbp
0x1800319ba  pop     rbx
0x1800319bb  retn
```
