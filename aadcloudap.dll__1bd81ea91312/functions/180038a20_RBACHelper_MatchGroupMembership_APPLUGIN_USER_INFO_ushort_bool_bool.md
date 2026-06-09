# RBACHelper::MatchGroupMembership(_APPLUGIN_USER_INFO *,ushort *,bool,bool *)

- ea: `0x180038a20`
- end: `0x180038be4`
- name: `?MatchGroupMembership@RBACHelper@@CAJPEAU_APPLUGIN_USER_INFO@@PEAG_NPEA_N@Z`
- size: `452`
- prototype: `static int(struct _APPLUGIN_USER_INFO *, unsigned __int16 *, bool, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003901c`

## callees

- `0x1800069c0`
- `0x180006ac4`
- `0x180038a20`
- `0x180071e14`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180038b1b`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180038b48`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180038b1b`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180038b48`
- `samcli!NetLocalGroupGetMembers` at `0x180038ad4`
- `samcli!NetLocalGroupGetMembers` at `0x180038ad4`
- `netutils!NetApiBufferFree` at `0x180038bb4`
- `netutils!NetApiBufferFree` at `0x180038bb4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RBACHelper::MatchGroupMembership(PSID *a1, unsigned __int16 *a2, char a3, bool *a4)
{
  signed int Members; // eax
  __int64 i; // rbx
  bool v10; // al
  __int64 v11; // rsi
  unsigned int v12; // ebx
  __int64 prefmaxlen; // [rsp+20h] [rbp-39h]
  LPDWORD totalentries; // [rsp+30h] [rbp-29h]
  DWORD entriesread; // [rsp+50h] [rbp-9h] BYREF
  DWORD v17; // [rsp+54h] [rbp-5h] BYREF
  LPBYTE bufptr; // [rsp+58h] [rbp-1h] BYREF
  const char *v19[6]; // [rsp+60h] [rbp+7h] BYREF
  int v20; // [rsp+C0h] [rbp+67h] BYREF

  v20 = 0;
  bufptr = 0;
  entriesread = 0;
  v17 = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v19,
    (int)"rbachelper.cpp",
    (int)"RBACHelper::MatchGroupMembership",
    (int)&v20);
  if ( !a1 || !a2 || !a4 )
  {
    Members = -1073741811;
    v20 = -1073741811;
    LODWORD(totalentries) = 334;
    goto LABEL_19;
  }
  *a4 = 0;
  Members = NetLocalGroupGetMembers(0, a2, 0, &bufptr, 0xFFFFFFFF, &entriesread, &v17, 0);
  v20 = Members;
  if ( Members < 0 )
  {
    LODWORD(totalentries) = 339;
LABEL_19:
    LODWORD(prefmaxlen) = Members;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, prefmaxlen, "rbachelper.cpp", totalentries, "NTSTATUS", &base);
    goto LABEL_20;
  }
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    v10 = 0;
    if ( (unsigned int)i >= entriesread )
      break;
    if ( EqualSid(a1[2], *(PSID *)&bufptr[8 * i]) )
      goto LABEL_16;
    if ( a3 && *((_DWORD *)a1 + 6) && a1[4] )
    {
      v11 = 0;
      while ( !EqualSid(*((PSID *)a1[4] + v11), *(PSID *)&bufptr[8 * i]) )
      {
        v11 = (unsigned int)(v11 + 1);
        if ( (unsigned int)v11 >= *((_DWORD *)a1 + 6) )
          goto LABEL_15;
      }
LABEL_16:
      v10 = 1;
      break;
    }
LABEL_15:
    ;
  }
  *a4 = v10;
LABEL_20:
  if ( bufptr )
    NetApiBufferFree(bufptr);
  v12 = v20;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v19);
  return v12;
}

```

## disassembly

```asm
0x180038a20  mov     [rsp-8+arg_8], rbx
0x180038a25  mov     [rsp-8+arg_10], rsi
0x180038a2a  push    rbp
0x180038a2b  push    rdi
0x180038a2c  push    r12
0x180038a2e  push    r14
0x180038a30  push    r15
0x180038a32  lea     rbp, [rsp-37h]
0x180038a37  sub     rsp, 90h
0x180038a3e  mov     r14, r9
0x180038a41  mov     r12b, r8b
0x180038a44  mov     rbx, rdx
0x180038a47  mov     rdi, rcx
0x180038a4a  mov     [rbp+57h+arg_0], 0
0x180038a51  mov     [rbp+57h+bufptr], 0
0x180038a59  mov     [rbp+57h+var_60], 0
0x180038a60  mov     [rbp+57h+var_5C], 0
0x180038a67  lea     r9, [rbp+57h+arg_0]
0x180038a6b  lea     r8, aRbachelperMatc; "RBACHelper::MatchGroupMembership"
0x180038a72  lea     rsi, aOnecoreuapDsEx_18+21h; "rbachelper.cpp"
0x180038a79  mov     rdx, rsi
0x180038a7c  lea     rcx, [rbp+57h+var_50]
0x180038a80  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x180038a85  nop
0x180038a86  test    rdi, rdi
0x180038a89  jz      loc_180038B64
0x180038a8f  test    rbx, rbx
0x180038a92  jz      loc_180038B64
0x180038a98  test    r14, r14
0x180038a9b  jz      loc_180038B64
0x180038aa1  mov     byte ptr [r14], 0
0x180038aa5  mov     [rsp+0B0h+resumehandle], 0; resumehandle
0x180038aae  lea     rax, [rbp+57h+var_5C]
0x180038ab2  mov     [rsp+0B0h+totalentries], rax; totalentries
0x180038ab7  lea     rax, [rbp+57h+var_60]
0x180038abb  mov     [rsp+0B0h+entriesread], rax; entriesread
0x180038ac0  mov     dword ptr [rsp+0B0h+prefmaxlen], 0FFFFFFFFh; prefmaxlen
0x180038ac8  lea     r9, [rbp+57h+bufptr]; bufptr
0x180038acc  xor     r8d, r8d; level
0x180038acf  mov     rdx, rbx; localgroupname
0x180038ad2  xor     ecx, ecx; servername
0x180038ad4  call    cs:__imp_NetLocalGroupGetMembers
0x180038ada  mov     [rbp+57h+arg_0], eax
0x180038add  test    eax, eax
0x180038adf  jns     short loc_180038B06
0x180038ae1  lea     rcx, base
0x180038ae8  mov     [rsp+0B0h+var_70], rcx
0x180038aed  lea     rcx, aNtstatus; "NTSTATUS"
0x180038af4  mov     [rsp+0B0h+resumehandle], rcx
0x180038af9  mov     dword ptr [rsp+0B0h+totalentries], 153h
0x180038b01  jmp     loc_180038B8C
0x180038b06  xor     ebx, ebx
0x180038b08  xor     al, al
0x180038b0a  cmp     ebx, [rbp+57h+var_60]
0x180038b0d  jnb     short loc_180038B5F
0x180038b0f  mov     rdx, [rbp+57h+bufptr]
0x180038b13  mov     rdx, [rdx+rbx*8]; pSid2
0x180038b17  mov     rcx, [rdi+10h]; pSid1
0x180038b1b  call    cs:__imp_EqualSid
0x180038b21  test    eax, eax
0x180038b23  jnz     short loc_180038B5D
0x180038b25  test    r12b, r12b
0x180038b28  jz      short loc_180038B59
0x180038b2a  cmp     [rdi+18h], eax
0x180038b2d  jbe     short loc_180038B59
0x180038b2f  cmp     qword ptr [rdi+20h], 0
0x180038b34  jz      short loc_180038B59
0x180038b36  xor     esi, esi
0x180038b38  mov     rcx, [rdi+20h]
0x180038b3c  mov     rdx, [rbp+57h+bufptr]
0x180038b40  mov     rdx, [rdx+rbx*8]; pSid2
0x180038b44  mov     rcx, [rcx+rsi*8]; pSid1
0x180038b48  call    cs:__imp_EqualSid
0x180038b4e  test    eax, eax
0x180038b50  jnz     short loc_180038B5D
0x180038b52  inc     esi
0x180038b54  cmp     esi, [rdi+18h]
0x180038b57  jb      short loc_180038B38
0x180038b59  inc     ebx
0x180038b5b  jmp     short loc_180038B08
0x180038b5d  mov     al, 1
0x180038b5f  mov     [r14], al
0x180038b62  jmp     short loc_180038BAB
0x180038b64  mov     eax, 0C000000Dh
0x180038b69  mov     [rbp+57h+arg_0], eax
0x180038b6c  lea     rcx, base
0x180038b73  mov     [rsp+0B0h+var_70], rcx
0x180038b78  lea     rcx, aNtstatus; "NTSTATUS"
0x180038b7f  mov     [rsp+0B0h+resumehandle], rcx
0x180038b84  mov     dword ptr [rsp+0B0h+totalentries], 14Eh
0x180038b8c  mov     [rsp+0B0h+entriesread], rsi
0x180038b91  mov     ecx, 2
0x180038b96  mov     dword ptr [rsp+0B0h+prefmaxlen], eax
0x180038b9a  mov     r9d, ecx
0x180038b9d  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180038ba4  xor     edx, edx
0x180038ba6  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180038bab  mov     rcx, [rbp+57h+bufptr]; Buffer
0x180038baf  test    rcx, rcx
0x180038bb2  jz      short loc_180038BBA
0x180038bb4  call    cs:__imp_NetApiBufferFree
0x180038bba  mov     ebx, [rbp+57h+arg_0]
0x180038bbd  lea     rcx, [rbp+57h+var_50]
0x180038bc1  call    ??1?$DbgTracePrintHelper@J@@QEAA@XZ; DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(void)
0x180038bc6  mov     eax, ebx
0x180038bc8  lea     r11, [rsp+0B0h+var_20]
0x180038bd0  mov     rbx, [r11+38h]
0x180038bd4  mov     rsi, [r11+40h]
0x180038bd8  mov     rsp, r11
0x180038bdb  pop     r15
0x180038bdd  pop     r14
0x180038bdf  pop     r12
0x180038be1  pop     rdi
0x180038be2  pop     rbp
0x180038be3  retn
```
