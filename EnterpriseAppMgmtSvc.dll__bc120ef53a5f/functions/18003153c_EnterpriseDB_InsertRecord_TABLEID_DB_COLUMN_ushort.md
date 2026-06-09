# EnterpriseDB::InsertRecord(TABLEID,DB_COLUMN *,ushort)

- ea: `0x18003153c`
- end: `0x180031817`
- name: `?InsertRecord@EnterpriseDB@@QEAAJW4TABLEID@@PEAUDB_COLUMN@@G@Z`
- size: `731`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013eb4`
- `0x18001a868`
- `0x18001b9f4`

## callees

- `0x180006ac0`
- `0x18003153c`
- `0x18006c8d2`
- `0x18006c910`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180031650`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180031650`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003168d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003168d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800316ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800316ac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800317cb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800317cb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003159f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003159f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800316ed`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800316ed`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031741`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031741`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003169e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800317e1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003169e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800317e1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180031781`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180031781`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180031794`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180031794`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall EnterpriseDB::InsertRecord(__int64 a1, int a2, __int64 a3, unsigned __int16 a4)
{
  unsigned int v4; // esi
  __int64 v6; // rbx
  int v8; // r14d
  __int64 v9; // rcx
  unsigned int v10; // ebx
  LPCWSTR *v11; // rax
  LPCWSTR v12; // r12
  int v13; // r15d
  __int64 v14; // rdx
  unsigned int i; // r8d
  HKEY v16; // rdi
  LSTATUS v17; // eax
  int v18; // esi
  HKEY hKey; // [rsp+50h] [rbp-69h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-61h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+60h] [rbp-59h]
  char v23; // [rsp+68h] [rbp-51h]
  GUID rguid; // [rsp+70h] [rbp-49h] BYREF
  OLECHAR sz[40]; // [rsp+80h] [rbp-39h] BYREF

  v4 = a4;
  v6 = a2;
  v8 = 0;
  hKey = 0;
  dwDisposition = 0;
  memset_0(sz, 0, sizeof(sz));
  rguid = 0;
  lpCriticalSection = (LPCRITICAL_SECTION)(a1 + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
  v23 = 1;
  if ( !a3 )
    goto LABEL_32;
  if ( !*(_DWORD *)a1 )
  {
LABEL_3:
    v10 = -2147467259;
    goto LABEL_33;
  }
  if ( (unsigned int)v6 > 1 )
    goto LABEL_32;
  v9 = 3 * v6;
  v11 = &(&g_TableInfo)[3 * v6];
  if ( !v11 )
    goto LABEL_32;
  v12 = v11[2];
  if ( !v12 )
    goto LABEL_32;
  v13 = v4;
  if ( !v4 )
    goto LABEL_32;
  v14 = 0;
  for ( i = 0; i < v4; ++i )
  {
    v9 = 3LL * i;
    if ( *(_WORD *)(a3 + 24LL * i) == *((_WORD *)v11 + 6) )
      v14 = a3 + 24LL * i;
  }
  if ( !v14 )
  {
LABEL_32:
    v10 = -2147024809;
    goto LABEL_33;
  }
  rguid = *(GUID *)*(_QWORD *)(v14 + 8);
  if ( !StringFromGUID2(&rguid, sz, 40) )
    goto LABEL_3;
  v16 = (_DWORD)v6 ? *(HKEY *)(a1 + 16) : *(HKEY *)(a1 + 8);
  if ( !v16 )
    goto LABEL_3;
  hKey = 0;
  v17 = RegCreateKeyExW(v16, sz, 0, 0, 0, 0xF003Fu, 0, &hKey, &dwDisposition);
  v10 = v17;
  if ( v17 )
  {
    if ( v17 <= 0 )
      goto LABEL_29;
LABEL_28:
    v10 = (unsigned __int16)v17 | 0x80070000;
    goto LABEL_29;
  }
  if ( dwDisposition != 1 )
  {
    v10 = -2147024713;
    goto LABEL_33;
  }
  v10 = 0;
  v18 = 0;
  v8 = 1;
  while ( 1 )
  {
    v17 = RegSetValueExW(
            hKey,
            *(LPCWSTR *)&v12[8 * *(unsigned __int16 *)(a3 + 24LL * v18)],
            0,
            *(_DWORD *)&v12[8 * *(unsigned __int16 *)(a3 + 24LL * v18) + 4],
            *(const BYTE **)(a3 + 24LL * v18 + 8),
            *(_DWORD *)(a3 + 24LL * v18 + 16));
    if ( v17 )
      break;
    if ( ++v18 >= v13 )
      goto LABEL_35;
  }
  if ( v17 > 0 )
    goto LABEL_28;
  v10 = v17;
LABEL_29:
  if ( (v10 & 0x80000000) == 0 )
    goto LABEL_35;
  if ( v8 )
  {
    RegDeleteTreeW(hKey, 0);
    RegDeleteKeyW(v16, sz);
  }
LABEL_33:
  if ( (Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits & 0x100) != 0 )
    McTemplateU0zq_EventWriteTransfer(v9, EnterpriseAppDBError, L"Insert Record Failed", v10);
LABEL_35:
  LeaveCriticalSection(lpCriticalSection);
  if ( hKey )
    RegCloseKey(hKey);
  return v10;
}

```

## disassembly

```asm
0x18003153c  mov     [rsp-8+arg_18], rbx
0x180031541  push    rbp
0x180031542  push    rsi
0x180031543  push    rdi
0x180031544  push    r12
0x180031546  push    r13
0x180031548  push    r14
0x18003154a  push    r15
0x18003154c  lea     rbp, [rsp-27h]
0x180031551  sub     rsp, 0E0h
0x180031558  mov     rax, cs:__security_cookie
0x18003155f  xor     rax, rsp
0x180031562  mov     [rbp+57h+var_40], rax
0x180031566  movzx   esi, r9w
0x18003156a  mov     r13, r8
0x18003156d  movsxd  rbx, edx
0x180031570  mov     rdi, rcx
0x180031573  xor     r14d, r14d
0x180031576  mov     [rbp+57h+hKey], r14
0x18003157a  mov     [rbp+57h+dwDisposition], r14d
0x18003157e  xor     edx, edx; Val
0x180031580  lea     r8d, [r14+50h]; Size
0x180031584  lea     rcx, [rbp+57h+sz]; void *
0x180031588  call    memset_0
0x18003158d  xorps   xmm0, xmm0
0x180031590  movups  xmmword ptr [rbp+57h+rguid.Data1], xmm0
0x180031594  lea     rax, [rdi+18h]
0x180031598  mov     [rbp+57h+lpCriticalSection], rax
0x18003159c  mov     rcx, rax; lpCriticalSection
0x18003159f  call    cs:__imp_EnterCriticalSection
0x1800315a6  nop     dword ptr [rax+rax+00h]
0x1800315ab  mov     [rbp+57h+var_A8], 1
0x1800315af  test    r13, r13
0x1800315b2  jz      loc_1800317A2
0x1800315b8  cmp     [rdi], r14d
0x1800315bb  jnz     short loc_1800315C7
0x1800315bd  mov     ebx, 80004005h
0x1800315c2  jmp     loc_1800317A7
0x1800315c7  cmp     ebx, 1
0x1800315ca  ja      loc_1800317A2
0x1800315d0  lea     rcx, [rbx+rbx*2]
0x1800315d4  lea     rax, ?g_TableInfo@@3PAUTABLE_INFO@@A; TABLE_INFO near * g_TableInfo
0x1800315db  lea     rax, [rax+rcx*8]
0x1800315df  test    rax, rax
0x1800315e2  jz      loc_1800317A2
0x1800315e8  mov     r12, [rax+10h]
0x1800315ec  test    r12, r12
0x1800315ef  jz      loc_1800317A2
0x1800315f5  mov     r15d, esi
0x1800315f8  test    esi, esi
0x1800315fa  jz      loc_1800317A2
0x180031600  mov     rdx, r14
0x180031603  mov     r8d, r14d
0x180031606  movzx   r9d, word ptr [rax+0Ch]
0x18003160b  mov     eax, r8d
0x18003160e  lea     rcx, [rax+rax*2]
0x180031612  lea     rax, ds:0[rcx*8]
0x18003161a  add     rax, r13
0x18003161d  cmp     [rax], r9w
0x180031621  cmovz   rdx, rax
0x180031625  inc     r8d
0x180031628  cmp     r8d, r15d
0x18003162b  jb      short loc_18003160B
0x18003162d  test    rdx, rdx
0x180031630  jz      loc_1800317A2
0x180031636  mov     rax, [rdx+8]
0x18003163a  movups  xmm0, xmmword ptr [rax]
0x18003163d  movdqu  xmmword ptr [rbp+57h+rguid.Data1], xmm0
0x180031642  mov     r8d, 28h ; '('; cchMax
0x180031648  lea     rdx, [rbp+57h+sz]; lpsz
0x18003164c  lea     rcx, [rbp+57h+rguid]; rguid
0x180031650  call    cs:__imp_StringFromGUID2
0x180031657  nop     dword ptr [rax+rax+00h]
0x18003165c  test    eax, eax
0x18003165e  jz      loc_1800315BD
0x180031664  test    ebx, ebx
0x180031666  jz      short loc_180031677
0x180031668  cmp     ebx, 1
0x18003166b  jnz     loc_1800315BD
0x180031671  mov     rdi, [rdi+10h]
0x180031675  jmp     short loc_18003167B
0x180031677  mov     rdi, [rdi+8]
0x18003167b  test    rdi, rdi
0x18003167e  jz      loc_1800315BD
0x180031684  mov     rsi, [rbp+57h+hKey]
0x180031688  test    rsi, rsi
0x18003168b  jz      short loc_1800316B8
0x18003168d  call    cs:__imp_GetLastError
0x180031694  nop     dword ptr [rax+rax+00h]
0x180031699  mov     ebx, eax
0x18003169b  mov     rcx, rsi; hKey
0x18003169e  call    cs:__imp_RegCloseKey
0x1800316a5  nop     dword ptr [rax+rax+00h]
0x1800316aa  mov     ecx, ebx; dwErrCode
0x1800316ac  call    cs:__imp_SetLastError
0x1800316b3  nop     dword ptr [rax+rax+00h]
0x1800316b8  mov     [rbp+57h+hKey], r14
0x1800316bc  lea     rax, [rbp+57h+dwDisposition]
0x1800316c0  mov     [rsp+110h+lpdwDisposition], rax; lpdwDisposition
0x1800316c5  lea     rax, [rbp+57h+hKey]
0x1800316c9  mov     [rsp+110h+phkResult], rax; phkResult
0x1800316ce  mov     [rsp+110h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1800316d3  mov     [rsp+110h+samDesired], 0F003Fh; samDesired
0x1800316db  mov     [rsp+110h+dwOptions], r14d; dwOptions
0x1800316e0  xor     r9d, r9d; lpClass
0x1800316e3  xor     r8d, r8d; Reserved
0x1800316e6  lea     rdx, [rbp+57h+sz]; lpSubKey
0x1800316ea  mov     rcx, rdi; hKey
0x1800316ed  call    cs:__imp_RegCreateKeyExW
0x1800316f4  nop     dword ptr [rax+rax+00h]
0x1800316f9  mov     ebx, eax
0x1800316fb  test    eax, eax
0x1800316fd  jnz     short loc_180031767
0x1800316ff  cmp     [rbp+57h+dwDisposition], 1
0x180031703  jnz     short loc_180031760
0x180031705  mov     ebx, r14d
0x180031708  xor     esi, esi
0x18003170a  lea     r14d, [rax+1]
0x18003170e  movsxd  rax, esi
0x180031711  lea     r8, [rax+rax*2]
0x180031715  movzx   edx, word ptr [r13+r8*8+0]
0x18003171b  add     rdx, rdx
0x18003171e  mov     eax, [r13+r8*8+10h]
0x180031723  mov     [rsp+110h+samDesired], eax; cbData
0x180031727  mov     rax, [r13+r8*8+8]
0x18003172c  mov     qword ptr [rsp+110h+dwOptions], rax; lpData
0x180031731  mov     r9d, [r12+rdx*8+8]; dwType
0x180031736  xor     r8d, r8d; Reserved
0x180031739  mov     rdx, [r12+rdx*8]; lpValueName
0x18003173d  mov     rcx, [rbp+57h+hKey]; hKey
0x180031741  call    cs:__imp_RegSetValueExW
0x180031748  nop     dword ptr [rax+rax+00h]
0x18003174d  test    eax, eax
0x18003174f  jnz     short loc_18003175A
0x180031751  inc     esi
0x180031753  cmp     esi, r15d
0x180031756  jl      short loc_18003170E
0x180031758  jmp     short loc_1800317C7
0x18003175a  jg      short loc_180031769
0x18003175c  mov     ebx, eax
0x18003175e  jmp     short loc_180031772
0x180031760  mov     ebx, 800700B7h
0x180031765  jmp     short loc_1800317A7
0x180031767  jle     short loc_180031772
0x180031769  movzx   ebx, ax
0x18003176c  or      ebx, 80070000h
0x180031772  test    ebx, ebx
0x180031774  jns     short loc_1800317C7
0x180031776  test    r14d, r14d
0x180031779  jz      short loc_1800317A7
0x18003177b  xor     edx, edx; lpSubKey
0x18003177d  mov     rcx, [rbp+57h+hKey]; hKey
0x180031781  call    cs:__imp_RegDeleteTreeW
0x180031788  nop     dword ptr [rax+rax+00h]
0x18003178d  lea     rdx, [rbp+57h+sz]; lpSubKey
0x180031791  mov     rcx, rdi; hKey
0x180031794  call    cs:__imp_RegDeleteKeyW
0x18003179b  nop     dword ptr [rax+rax+00h]
0x1800317a0  jmp     short loc_1800317A7
0x1800317a2  mov     ebx, 80070057h
0x1800317a7  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits+1, 1
0x1800317ae  jz      short loc_1800317C7
0x1800317b0  mov     r9d, ebx
0x1800317b3  lea     r8, aInsertRecordFa; "Insert Record Failed"
0x1800317ba  lea     rdx, EnterpriseAppDBError
0x1800317c1  call    McTemplateU0zq_EventWriteTransfer
0x1800317c6  nop
0x1800317c7  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x1800317cb  call    cs:__imp_LeaveCriticalSection
0x1800317d2  nop     dword ptr [rax+rax+00h]
0x1800317d7  nop
0x1800317d8  mov     rcx, [rbp+57h+hKey]; hKey
0x1800317dc  test    rcx, rcx
0x1800317df  jz      short loc_1800317ED
0x1800317e1  call    cs:__imp_RegCloseKey
0x1800317e8  nop     dword ptr [rax+rax+00h]
0x1800317ed  mov     eax, ebx
0x1800317ef  mov     rcx, [rbp+57h+var_40]
0x1800317f3  xor     rcx, rsp; StackCookie
0x1800317f6  call    __security_check_cookie
0x1800317fb  mov     rbx, [rsp+110h+arg_18]
0x180031803  add     rsp, 0E0h
0x18003180a  pop     r15
0x18003180c  pop     r14
0x18003180e  pop     r13
0x180031810  pop     r12
0x180031812  pop     rdi
0x180031813  pop     rsi
0x180031814  pop     rbp
0x180031815  retn
```
