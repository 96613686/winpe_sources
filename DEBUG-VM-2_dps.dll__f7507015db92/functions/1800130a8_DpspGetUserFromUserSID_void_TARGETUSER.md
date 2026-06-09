# DpspGetUserFromUserSID(void *,__TARGETUSER * *)

- ea: `0x1800130a8`
- end: `0x180013142`
- name: `?DpspGetUserFromUserSID@@YAJPEAXPEAPEAU__TARGETUSER@@@Z`
- size: `154`
- prototype: `__int64 __fastcall(PSID pSid1, struct __TARGETUSER **)`
- caller_count: `5`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180007adc`
- `0x1800146b0`
- `0x1800149dc`
- `0x180014df0`
- `0x180015918`

## callees

- `0x180009090`
- `0x1800130a8`

## import_xrefs

- `ntdll!RtlFirstEntrySList` at `0x180013106`
- `ntdll!RtlFirstEntrySList` at `0x180013106`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001311e`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001311e`

## string_xrefs

- `0x1800130d3`: `DpspGetUserFromUserSID`

## pseudocode

```c
__int64 __fastcall DpspGetUserFromUserSID(PSID pSid1, PSLIST_ENTRY *a2)
{
  int v4; // r8d
  unsigned int v5; // esi
  PSLIST_ENTRY EntrySList; // rbx
  struct _SLIST_ENTRY *Next; // r14

  if ( !pSid1 )
  {
    v4 = 657;
LABEL_3:
    v5 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
      (int)L"DpspGetUserFromUserSID",
      v4,
      (int)L"Error = %d",
      87);
    return v5;
  }
  if ( !a2 )
  {
    v4 = 658;
    goto LABEL_3;
  }
  v5 = 0;
  *a2 = 0;
  EntrySList = RtlFirstEntrySList(&g_QueuedResolutionListHead);
  if ( EntrySList )
  {
    while ( 1 )
    {
      Next = EntrySList->Next;
      if ( EqualSid(pSid1, EntrySList[4].Next) )
        break;
      EntrySList = Next;
      if ( !Next )
        return v5;
    }
    *a2 = EntrySList;
  }
  return v5;
}

```

## disassembly

```asm
0x1800130a8  push    rbx
0x1800130aa  push    rbp
0x1800130ab  push    rsi
0x1800130ac  push    rdi
0x1800130ad  push    r14
0x1800130af  sub     rsp, 30h
0x1800130b3  mov     rdi, rdx
0x1800130b6  mov     rbp, rcx
0x1800130b9  test    rcx, rcx
0x1800130bc  jnz     short loc_1800130ED
0x1800130be  mov     r8d, 291h; int
0x1800130c4  lea     r9, aErrorD; "Error = %d"
0x1800130cb  mov     dword ptr [rsp+58h+Args], 57h ; 'W'; Args
0x1800130d3  lea     rdx, aDpspgetuserfro; "DpspGetUserFromUserSID"
0x1800130da  mov     esi, 80070057h
0x1800130df  lea     rcx, aClientcoreBase_2; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800130e6  call    WdipTraceError
0x1800130eb  jmp     short loc_180013135
0x1800130ed  test    rdi, rdi
0x1800130f0  jnz     short loc_1800130FA
0x1800130f2  mov     r8d, 292h
0x1800130f8  jmp     short loc_1800130C4
0x1800130fa  xor     esi, esi
0x1800130fc  lea     rcx, g_QueuedResolutionListHead; ListHead
0x180013103  mov     [rdx], rsi
0x180013106  call    cs:__imp_RtlFirstEntrySList
0x18001310c  mov     rbx, rax
0x18001310f  test    rax, rax
0x180013112  jz      short loc_180013135
0x180013114  mov     rdx, [rbx+40h]; pSid2
0x180013118  mov     rcx, rbp; pSid1
0x18001311b  mov     r14, [rbx]
0x18001311e  call    cs:__imp_EqualSid
0x180013124  test    eax, eax
0x180013126  jnz     short loc_180013132
0x180013128  mov     rbx, r14
0x18001312b  test    r14, r14
0x18001312e  jnz     short loc_180013114
0x180013130  jmp     short loc_180013135
0x180013132  mov     [rdi], rbx
0x180013135  mov     eax, esi
0x180013137  add     rsp, 30h
0x18001313b  pop     r14
0x18001313d  pop     rdi
0x18001313e  pop     rsi
0x18001313f  pop     rbp
0x180013140  pop     rbx
0x180013141  retn
```
