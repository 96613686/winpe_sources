# CAuthenticatorList::Check(void *,ulong,void *,ulong,_LARGE_INTEGER *,uchar,uchar,uchar)

- ea: `0x180083990`
- end: `0x180083c27`
- name: `?Check@CAuthenticatorList@@QEAAJPEAXK0KPEAT_LARGE_INTEGER@@EEE@Z`
- size: `663`
- prototype: `__int64 __fastcall(PRTL_GENERIC_TABLE Table, void *, unsigned int, void *, unsigned int, union _LARGE_INTEGER *, unsigned __int8, unsigned __int8, unsigned __int8)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180014c9c`
- `0x18001e930`
- `0x18007dd38`

## callees

- `0x180002ad0`
- `0x1800101c4`
- `0x1800829a0`
- `0x1800829e4`
- `0x180082a2c`
- `0x1800838fc`
- `0x180083990`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800839d5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800839d5`
- `ntdll!RtlLeaveCriticalSection` at `0x180083bf7`
- `ntdll!RtlLeaveCriticalSection` at `0x180083bf7`
- `ntdll!RtlEnterCriticalSection` at `0x180083a23`
- `ntdll!RtlEnterCriticalSection` at `0x180083a23`
- `ntdll!RtlDeleteElementGenericTable` at `0x180083b75`
- `ntdll!RtlDeleteElementGenericTable` at `0x180083b75`
- `ntdll!RtlInsertElementGenericTable` at `0x180083ab5`
- `ntdll!RtlInsertElementGenericTable` at `0x180083ab5`
- `ntdll!RtlLookupElementGenericTable` at `0x180083b57`
- `ntdll!RtlLookupElementGenericTable` at `0x180083b57`

## pseudocode

```c
__int64 __fastcall CAuthenticatorList::Check(
        PRTL_GENERIC_TABLE Table,
        void *a2,
        unsigned int a3,
        void *a4,
        unsigned int a5,
        union _LARGE_INTEGER *a6,
        unsigned __int8 a7,
        unsigned __int8 a8,
        unsigned __int8 a9)
{
  PRTL_SPLAY_LINKS TableRoot; // rdx
  unsigned int v13; // ebx
  _DWORD *inserted; // rax
  CSecurityData *v15; // rcx
  __int64 v16; // rdx
  _DWORD *v17; // rax
  unsigned __int8 NewElement[4]; // [rsp+20h] [rbp-98h] BYREF
  int v20; // [rsp+24h] [rbp-94h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+28h] [rbp-90h] BYREF
  union _LARGE_INTEGER v22; // [rsp+30h] [rbp-88h] BYREF
  union _LARGE_INTEGER v23; // [rsp+38h] [rbp-80h] BYREF
  struct _LIST_ENTRY **p_Blink; // [rsp+40h] [rbp-78h]
  BCRYPT_HASH_HANDLE phHash[3]; // [rsp+48h] [rbp-70h] BYREF
  _OWORD Buffer[2]; // [rsp+60h] [rbp-58h] BYREF

  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  TableRoot = Table[1].TableRoot;
  v23.QuadPart = *(_QWORD *)&SystemTimeAsFileTime - (_QWORD)TableRoot;
  v22.QuadPart = (LONGLONG)TableRoot + *(_QWORD *)&SystemTimeAsFileTime;
  if ( a6->QuadPart < *(_QWORD *)&SystemTimeAsFileTime - (_QWORD)TableRoot
    || (v13 = 0, a6->QuadPart > (__int64)TableRoot + *(_QWORD *)&SystemTimeAsFileTime) )
  {
    v13 = 37;
  }
  if ( a9 )
  {
    p_Blink = &Table[1].InsertOrderList.Blink;
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)&Table[1].InsertOrderList.Blink);
    CAuthenticatorList::Age(Table, &v23, &v22);
    NewElement[0] = 0;
    memset(Buffer, 0, sizeof(Buffer));
    memset(phHash, 0, sizeof(phHash));
    *(union _LARGE_INTEGER *)&Buffer[0] = *a6;
    CngRsa32Compat_MD5Init(phHash);
    CngRsa32Compat_MD5Update(phHash, a2, a3);
    CngRsa32Compat_MD5Final(phHash);
    *(_OWORD *)((char *)Buffer + 12) = *(_OWORD *)&phHash[1];
    if ( a7 )
    {
      inserted = RtlInsertElementGenericTable(Table, Buffer, 0x20u, NewElement);
      if ( !inserted )
      {
        v13 = 60;
        v20 = 60;
LABEL_30:
        RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)&Table[1].InsertOrderList.Blink);
        return v13;
      }
      if ( NewElement[0] )
      {
        inserted[2] = 1;
        if ( !BYTE4(Table[1].InsertOrderList.Flink) )
          goto LABEL_30;
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_30;
        }
        v16 = 10;
      }
      else
      {
        if ( ++inserted[2] < LODWORD(Table[1].InsertOrderList.Flink) )
          goto LABEL_30;
        v13 = 34;
        v20 = 34;
        if ( !BYTE4(Table[1].InsertOrderList.Flink) )
          goto LABEL_30;
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_30;
        }
        v16 = 11;
      }
    }
    else
    {
      v17 = RtlLookupElementGenericTable(Table, Buffer);
      if ( !v17 )
        goto LABEL_30;
      if ( a8 )
      {
        RtlDeleteElementGenericTable(Table, v17);
        if ( !BYTE4(Table[1].InsertOrderList.Flink) )
          goto LABEL_30;
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_30;
        }
        v16 = 12;
      }
      else
      {
        if ( v17[2] < LODWORD(Table[1].InsertOrderList.Flink) )
          goto LABEL_30;
        v13 = 34;
        v20 = 34;
        if ( !BYTE4(Table[1].InsertOrderList.Flink) )
          goto LABEL_30;
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_30;
        }
        v16 = 13;
      }
    }
    WPP_SF_(*((_QWORD *)v15 + 2), v16, WPP_ca534e7a7fb3321a12b2f35c29d9b937_Traceguids);
    goto LABEL_30;
  }
  return v13;
}

```

## disassembly

```asm
0x180083990  mov     [rsp+arg_18], rbx
0x180083995  push    rsi
0x180083996  push    rdi
0x180083997  push    r12
0x180083999  push    r14
0x18008399b  push    r15
0x18008399d  sub     rsp, 90h
0x1800839a4  mov     rax, cs:__security_cookie
0x1800839ab  xor     rax, rsp
0x1800839ae  mov     [rsp+0B8h+var_38], rax
0x1800839b6  mov     r12d, r8d
0x1800839b9  mov     r15, rdx
0x1800839bc  mov     rdi, rcx
0x1800839bf  mov     r14, [rsp+0B8h+arg_28]
0x1800839c7  mov     qword ptr [rsp+0B8h+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800839d0  lea     rcx, [rsp+0B8h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800839d5  call    cs:__imp_GetSystemTimeAsFileTime
0x1800839db  mov     rdx, [rdi+48h]
0x1800839df  mov     rax, qword ptr [rsp+0B8h+SystemTimeAsFileTime.dwLowDateTime]
0x1800839e4  mov     rcx, rax
0x1800839e7  sub     rcx, rdx
0x1800839ea  mov     qword ptr [rsp+0B8h+var_80], rcx
0x1800839ef  lea     r8, [rdx+rax]
0x1800839f3  mov     qword ptr [rsp+0B8h+var_88], r8
0x1800839f8  cmp     [r14], rcx
0x1800839fb  jl      short loc_180083A04
0x1800839fd  xor     ebx, ebx
0x1800839ff  cmp     [r14], r8
0x180083a02  jle     short loc_180083A09
0x180083a04  mov     ebx, 25h ; '%'
0x180083a09  cmp     [rsp+0B8h+arg_40], 0
0x180083a11  jz      loc_180083BFD
0x180083a17  lea     rsi, [rdi+58h]
0x180083a1b  mov     [rsp+0B8h+var_78], rsi
0x180083a20  mov     rcx, rsi; CriticalSection
0x180083a23  call    cs:__imp_RtlEnterCriticalSection
0x180083a29  nop
0x180083a2a  lea     r8, [rsp+0B8h+var_88]; union _LARGE_INTEGER *
0x180083a2f  lea     rdx, [rsp+0B8h+var_80]; union _LARGE_INTEGER *
0x180083a34  mov     rcx, rdi; Table
0x180083a37  call    ?Age@CAuthenticatorList@@AEAAKAEBT_LARGE_INTEGER@@0@Z; CAuthenticatorList::Age(_LARGE_INTEGER const &,_LARGE_INTEGER const &)
0x180083a3c  mov     [rsp+0B8h+NewElement], 0
0x180083a41  xorps   xmm0, xmm0
0x180083a44  movups  [rsp+0B8h+Buffer], xmm0
0x180083a49  movups  [rsp+0B8h+var_48], xmm0
0x180083a4e  xorps   xmm1, xmm1
0x180083a51  xor     eax, eax
0x180083a53  movups  xmmword ptr [rsp+0B8h+phHash], xmm1
0x180083a58  mov     [rsp+0B8h+var_60], rax
0x180083a5d  mov     rax, [r14]
0x180083a60  mov     qword ptr [rsp+0B8h+Buffer], rax
0x180083a65  lea     rcx, [rsp+0B8h+phHash]; phHash
0x180083a6a  call    CngRsa32Compat_MD5Init
0x180083a6f  mov     r8d, r12d
0x180083a72  mov     rdx, r15
0x180083a75  lea     rcx, [rsp+0B8h+phHash]
0x180083a7a  call    CngRsa32Compat_MD5Update
0x180083a7f  lea     rcx, [rsp+0B8h+phHash]
0x180083a84  call    CngRsa32Compat_MD5Final
0x180083a89  movups  xmm0, xmmword ptr [rsp+0B8h+phHash+8]
0x180083a8e  movdqu  [rsp+0B8h+Buffer+0Ch], xmm0
0x180083a94  lea     rdx, [rsp+0B8h+Buffer]; Buffer
0x180083a99  mov     rcx, rdi; Table
0x180083a9c  cmp     [rsp+0B8h+arg_30], 0
0x180083aa4  jz      loc_180083B57
0x180083aaa  lea     r9, [rsp+0B8h+NewElement]; NewElement
0x180083aaf  mov     r8d, 20h ; ' '; BufferSize
0x180083ab5  call    cs:__imp_RtlInsertElementGenericTable
0x180083abb  test    rax, rax
0x180083abe  jnz     short loc_180083ACC
0x180083ac0  lea     ebx, [rax+3Ch]
0x180083ac3  mov     [rsp+0B8h+var_94], ebx
0x180083ac7  jmp     loc_180083BE4
0x180083acc  cmp     [rsp+0B8h+NewElement], 0
0x180083ad1  jz      short loc_180083B0F
0x180083ad3  mov     dword ptr [rax+8], 1
0x180083ada  cmp     byte ptr [rdi+54h], 0
0x180083ade  jz      loc_180083BE4
0x180083ae4  lea     rax, WPP_GLOBAL_Control
0x180083aeb  mov     rcx, cs:WPP_GLOBAL_Control
0x180083af2  cmp     rcx, rax
0x180083af5  jz      loc_180083BE4
0x180083afb  test    byte ptr [rcx+1Ch], 1
0x180083aff  jz      loc_180083BE4
0x180083b05  mov     edx, 0Ah
0x180083b0a  jmp     loc_180083BD4
0x180083b0f  inc     dword ptr [rax+8]
0x180083b12  mov     eax, [rax+8]
0x180083b15  cmp     eax, [rdi+50h]
0x180083b18  jb      loc_180083BE4
0x180083b1e  mov     ebx, 22h ; '"'
0x180083b23  mov     [rsp+0B8h+var_94], ebx
0x180083b27  cmp     byte ptr [rdi+54h], 0
0x180083b2b  jz      loc_180083BE4
0x180083b31  lea     rax, WPP_GLOBAL_Control
0x180083b38  mov     rcx, cs:WPP_GLOBAL_Control
0x180083b3f  cmp     rcx, rax
0x180083b42  jz      loc_180083BE4
0x180083b48  test    byte ptr [rcx+1Ch], 1
0x180083b4c  jz      loc_180083BE4
0x180083b52  lea     edx, [rbx-17h]
0x180083b55  jmp     short loc_180083BD4
0x180083b57  call    cs:__imp_RtlLookupElementGenericTable
0x180083b5d  mov     rcx, rax
0x180083b60  test    rax, rax
0x180083b63  jz      short loc_180083BE4
0x180083b65  cmp     [rsp+0B8h+arg_38], 0
0x180083b6d  jz      short loc_180083BA1
0x180083b6f  mov     rdx, rax; Buffer
0x180083b72  mov     rcx, rdi; Table
0x180083b75  call    cs:__imp_RtlDeleteElementGenericTable
0x180083b7b  cmp     byte ptr [rdi+54h], 0
0x180083b7f  jz      short loc_180083BE4
0x180083b81  lea     rax, WPP_GLOBAL_Control
0x180083b88  mov     rcx, cs:WPP_GLOBAL_Control
0x180083b8f  cmp     rcx, rax
0x180083b92  jz      short loc_180083BE4
0x180083b94  test    byte ptr [rcx+1Ch], 1
0x180083b98  jz      short loc_180083BE4
0x180083b9a  mov     edx, 0Ch
0x180083b9f  jmp     short loc_180083BD4
0x180083ba1  mov     eax, [rdi+50h]
0x180083ba4  cmp     [rcx+8], eax
0x180083ba7  jb      short loc_180083BE4
0x180083ba9  mov     ebx, 22h ; '"'
0x180083bae  mov     [rsp+0B8h+var_94], ebx
0x180083bb2  cmp     byte ptr [rdi+54h], 0
0x180083bb6  jz      short loc_180083BE4
0x180083bb8  lea     rax, WPP_GLOBAL_Control
0x180083bbf  mov     rcx, cs:WPP_GLOBAL_Control
0x180083bc6  cmp     rcx, rax
0x180083bc9  jz      short loc_180083BE4
0x180083bcb  test    byte ptr [rcx+1Ch], 1
0x180083bcf  jz      short loc_180083BE4
0x180083bd1  lea     edx, [rbx-15h]
0x180083bd4  lea     r8, WPP_ca534e7a7fb3321a12b2f35c29d9b937_Traceguids
0x180083bdb  mov     rcx, [rcx+10h]
0x180083bdf  call    WPP_SF_
0x180083be4  jmp     short loc_180083BF4
0x180083be6  mov     ebx, 3Ch ; '<'
0x180083beb  mov     [rsp+0B8h+var_94], ebx
0x180083bef  mov     rsi, [rsp+0B8h+var_78]
0x180083bf4  mov     rcx, rsi; CriticalSection
0x180083bf7  call    cs:__imp_RtlLeaveCriticalSection
0x180083bfd  mov     eax, ebx
0x180083bff  mov     rcx, [rsp+0B8h+var_38]
0x180083c07  xor     rcx, rsp; StackCookie
0x180083c0a  call    __security_check_cookie
0x180083c0f  mov     rbx, [rsp+0B8h+arg_18]
0x180083c17  add     rsp, 90h
0x180083c1e  pop     r15
0x180083c20  pop     r14
0x180083c22  pop     r12
0x180083c24  pop     rdi
0x180083c25  pop     rsi
0x180083c26  retn
```
