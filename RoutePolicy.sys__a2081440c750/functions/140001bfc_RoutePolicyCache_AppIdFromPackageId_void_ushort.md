# RoutePolicyCache::AppIdFromPackageId(void *,ushort * *)

- ea: `0x140001bfc`
- end: `0x140001d8e`
- name: `?AppIdFromPackageId@RoutePolicyCache@@YAJPEAXPEAPEAG@Z`
- size: `402`
- prototype: `__int64 __fastcall(PSID Sid2, RoutePolicyCache *this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x1400030dc`

## callees

- `0x140001008`
- `0x1400012f0`
- `0x140001aac`
- `0x140001bfc`
- `0x140007d28`
- `0x140007d7c`
- `0x14000a680`

## import_xrefs

- `ntoskrnl!RtlEqualSid` at `0x140001c58`
- `ntoskrnl!RtlEqualSid` at `0x140001c58`

## string_xrefs

- `0x140001d2c`: `Failed to copy AppId`

## pseudocode

```c
__int64 __fastcall RoutePolicyCache::AppIdFromPackageId(
        unsigned __int8 *Sid2,
        RoutePolicyCache *this,
        unsigned __int16 **a3)
{
  PVOID *i; // rbx
  const unsigned __int16 *v6; // r8
  int v7; // eax
  int v9; // eax
  int v10; // r8d
  int v11; // r9d
  unsigned int v12; // ebx
  __int128 v13; // [rsp+30h] [rbp-19h] BYREF
  int v14; // [rsp+40h] [rbp-9h] BYREF
  const char *v15; // [rsp+48h] [rbp-1h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v16; // [rsp+50h] [rbp+7h] BYREF
  unsigned __int8 *v17; // [rsp+70h] [rbp+27h]
  int v18; // [rsp+78h] [rbp+2Fh]
  int v19; // [rsp+7Ch] [rbp+33h]

  *(_QWORD *)this = 0;
  AcquireSpinLock(&v13, &g_cacheLock);
  for ( i = (PVOID *)g_packageListHead; ; i = (PVOID *)*i )
  {
    if ( i == &g_packageListHead )
    {
      if ( (unsigned int)dword_140012050 > 3 )
      {
        v7 = Sid2[1];
        v17 = Sid2;
        v19 = 0;
        v18 = 4 * v7 + 8;
        tlgWriteTransfer_EtwWriteTransfer((int)&dword_140012050, (int)&byte_14000E4A1, 0, 0, 3u, &v16);
      }
      if ( (_QWORD)v13 )
        SpinLockAndSavedIrql::Release((const struct SpinLockAndSavedIrql *)&v13);
      return 3221226021LL;
    }
    if ( RtlEqualSid(i[2], Sid2) )
      break;
  }
  v9 = RoutePolicyCache::AllocateAndCopyStringParameter(this, (unsigned __int16 **)i[3], v6);
  v12 = v9;
  if ( v9 >= 0 )
  {
    if ( (_QWORD)v13 )
      SpinLockAndSavedIrql::Release((const struct SpinLockAndSavedIrql *)&v13);
    return 0;
  }
  else
  {
    if ( (unsigned int)dword_140012050 > 2 )
    {
      v14 = v9;
      v15 = "Failed to copy AppId";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        dword_140012050,
        (unsigned int)&unk_14000E150,
        v10,
        v11,
        (__int64)&v15,
        (__int64)&v14);
    }
    if ( (_QWORD)v13 )
      SpinLockAndSavedIrql::Release((const struct SpinLockAndSavedIrql *)&v13);
    return v12;
  }
}

```

## disassembly

```asm
0x140001bfc  mov     [rsp-8+arg_10], rbx
0x140001c01  mov     [rsp-8+arg_18], rsi
0x140001c06  push    rbp
0x140001c07  push    rdi
0x140001c08  push    r15
0x140001c0a  lea     rbp, [rsp-47h]
0x140001c0f  sub     rsp, 90h
0x140001c16  mov     rax, cs:__security_cookie
0x140001c1d  xor     rax, rsp
0x140001c20  mov     [rbp+57h+var_20], rax
0x140001c24  mov     rsi, rdx
0x140001c27  mov     qword ptr [rdx], 0
0x140001c2e  mov     rdi, rcx
0x140001c31  lea     rdx, ?g_cacheLock@@3_KA; unsigned __int64 g_cacheLock
0x140001c38  lea     rcx, [rbp+57h+var_70]
0x140001c3c  call    ?AcquireSpinLock@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUSpinLockAndSavedIrql@@@Z$1?Release@1@SAX0@ZU?$integral_constant@_K$01@wistd@@U1@PEA_K$0A@$$T@details@wil@@@details@wil@@@wil@@PEA_K@Z; AcquireSpinLock(unsigned __int64 *)
0x140001c41  mov     rbx, cs:?g_packageListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_packageListHead
0x140001c48  lea     r15, ?g_packageListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_packageListHead
0x140001c4f  jmp     short loc_140001C6F
0x140001c51  mov     rcx, [rbx+10h]; Sid1
0x140001c55  mov     rdx, rdi; Sid2
0x140001c58  call    cs:__imp_RtlEqualSid
0x140001c5f  nop     dword ptr [rax+rax+00h]
0x140001c64  test    al, al
0x140001c66  jnz     loc_140001D05
0x140001c6c  mov     rbx, [rbx]
0x140001c6f  cmp     rbx, r15
0x140001c72  jnz     short loc_140001C51
0x140001c74  mov     eax, cs:dword_140012050
0x140001c7a  cmp     eax, 3
0x140001c7d  jbe     short loc_140001CC2
0x140001c7f  movzx   eax, byte ptr [rdi+1]
0x140001c83  lea     rdx, byte_14000E4A1; int
0x140001c8a  xor     r9d, r9d; int
0x140001c8d  mov     [rbp+57h+var_30], rdi
0x140001c91  xor     r8d, r8d; int
0x140001c94  mov     [rbp+57h+var_24], 0
0x140001c9b  lea     rcx, dword_140012050; int
0x140001ca2  lea     eax, ds:8[rax*4]
0x140001ca9  mov     [rbp+57h+var_28], eax
0x140001cac  lea     rax, [rbp+57h+var_50]
0x140001cb0  mov     [rsp+0A0h+var_78], rax; PEVENT_DATA_DESCRIPTOR
0x140001cb5  mov     [rsp+0A0h+var_80], 3; ULONG
0x140001cbd  call    _tlgWriteTransfer_EtwWriteTransfer
0x140001cc2  cmp     qword ptr [rbp+57h+var_70], 0
0x140001cc7  jz      short loc_140001CDB
0x140001cc9  movaps  xmm0, [rbp+57h+var_70]
0x140001ccd  lea     rcx, [rbp+57h+var_70]; struct SpinLockAndSavedIrql *
0x140001cd1  movdqa  [rbp+57h+var_70], xmm0
0x140001cd6  call    ?Release@SpinLockAndSavedIrql@@SAXAEBU1@@Z; SpinLockAndSavedIrql::Release(SpinLockAndSavedIrql const &)
0x140001cdb  mov     eax, 0C0000225h
0x140001ce0  mov     rcx, [rbp+57h+var_20]
0x140001ce4  xor     rcx, rsp; StackCookie
0x140001ce7  call    __security_check_cookie
0x140001cec  lea     r11, [rsp+0A0h+var_10]
0x140001cf4  mov     rbx, [r11+30h]
0x140001cf8  mov     rsi, [r11+38h]
0x140001cfc  mov     rsp, r11
0x140001cff  pop     r15
0x140001d01  pop     rdi
0x140001d02  pop     rbp
0x140001d03  retn
0x140001d05  mov     rdx, [rbx+18h]; unsigned __int16 **
0x140001d09  mov     rcx, rsi; this
0x140001d0c  call    ?AllocateAndCopyStringParameter@RoutePolicyCache@@YAJPEAPEAGPEBG@Z; RoutePolicyCache::AllocateAndCopyStringParameter(ushort * *,ushort const *)
0x140001d11  mov     ebx, eax
0x140001d13  test    eax, eax
0x140001d15  jns     short loc_140001D6E
0x140001d17  mov     ecx, cs:dword_140012050
0x140001d1d  cmp     ecx, 2
0x140001d20  jbe     short loc_140001D4E
0x140001d22  mov     [rbp+57h+var_60], eax
0x140001d25  lea     rdx, unk_14000E150
0x140001d2c  lea     rax, aFailedToCopyAp; "Failed to copy AppId"
0x140001d33  mov     [rbp+57h+var_58], rax
0x140001d37  lea     rax, [rbp+57h+var_60]
0x140001d3b  mov     [rsp+0A0h+var_78], rax
0x140001d40  lea     rax, [rbp+57h+var_58]
0x140001d44  mov     qword ptr [rsp+0A0h+var_80], rax
0x140001d49  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140001d4e  cmp     qword ptr [rbp+57h+var_70], 0
0x140001d53  jz      short loc_140001D67
0x140001d55  movaps  xmm0, [rbp+57h+var_70]
0x140001d59  lea     rcx, [rbp+57h+var_70]; struct SpinLockAndSavedIrql *
0x140001d5d  movdqa  [rbp+57h+var_70], xmm0
0x140001d62  call    ?Release@SpinLockAndSavedIrql@@SAXAEBU1@@Z; SpinLockAndSavedIrql::Release(SpinLockAndSavedIrql const &)
0x140001d67  mov     eax, ebx
0x140001d69  jmp     loc_140001CE0
0x140001d6e  cmp     qword ptr [rbp+57h+var_70], 0
0x140001d73  jz      short loc_140001D87
0x140001d75  movaps  xmm0, [rbp+57h+var_70]
0x140001d79  lea     rcx, [rbp+57h+var_70]; struct SpinLockAndSavedIrql *
0x140001d7d  movdqa  [rbp+57h+var_70], xmm0
0x140001d82  call    ?Release@SpinLockAndSavedIrql@@SAXAEBU1@@Z; SpinLockAndSavedIrql::Release(SpinLockAndSavedIrql const &)
0x140001d87  xor     eax, eax
0x140001d89  jmp     loc_140001CE0
```
