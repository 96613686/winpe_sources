# FaxRouteAddFile(ulong,ushort const *,_GUID *)

- ea: `0x140042940`
- end: `0x140042b2c`
- name: `?FaxRouteAddFile@@YAJKPEBGPEAU_GUID@@@Z`
- size: `492`
- prototype: `__int64 __fastcall(int, const unsigned __int16 *, struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400423a8`

## callees

- `0x140042940`
- `0x1400433e0`
- `0x140065d14`
- `0x140067168`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x140042b00`
- `KERNEL32!SetLastError` at `0x140042b00`
- `KERNEL32!EnterCriticalSection` at `0x1400429a7`
- `KERNEL32!EnterCriticalSection` at `0x1400429b4`
- `KERNEL32!EnterCriticalSection` at `0x140042a88`
- `KERNEL32!EnterCriticalSection` at `0x140042ab7`
- `KERNEL32!EnterCriticalSection` at `0x140042ac4`
- `KERNEL32!EnterCriticalSection` at `0x1400429a7`
- `KERNEL32!EnterCriticalSection` at `0x1400429b4`
- `KERNEL32!EnterCriticalSection` at `0x140042a88`
- `KERNEL32!EnterCriticalSection` at `0x140042ab7`
- `KERNEL32!EnterCriticalSection` at `0x140042ac4`
- `KERNEL32!LeaveCriticalSection` at `0x1400429e0`
- `KERNEL32!LeaveCriticalSection` at `0x1400429ed`
- `KERNEL32!LeaveCriticalSection` at `0x140042aaa`
- `KERNEL32!LeaveCriticalSection` at `0x140042add`
- `KERNEL32!LeaveCriticalSection` at `0x140042aea`
- `KERNEL32!LeaveCriticalSection` at `0x1400429e0`
- `KERNEL32!LeaveCriticalSection` at `0x1400429ed`
- `KERNEL32!LeaveCriticalSection` at `0x140042aaa`
- `KERNEL32!LeaveCriticalSection` at `0x140042add`
- `KERNEL32!LeaveCriticalSection` at `0x140042aea`
- `KERNEL32!GetFullPathNameW` at `0x140042a3d`
- `KERNEL32!GetFullPathNameW` at `0x140042a3d`
- `ole32!StringFromGUID2` at `0x14004299a`
- `ole32!StringFromGUID2` at `0x14004299a`

## pseudocode

```c
__int64 __fastcall FaxRouteAddFile(int a1, const unsigned __int16 *a2, struct _GUID *a3)
{
  struct _LIST_ENTRY *i; // rdi
  __int64 v7; // rsi
  DWORD v8; // ecx
  _QWORD *p_Flink; // rax
  unsigned int v10; // ebx
  LPWSTR FilePart; // [rsp+20h] [rbp-298h] BYREF
  OLECHAR sz[40]; // [rsp+30h] [rbp-288h] BYREF
  WCHAR Buffer[264]; // [rsp+80h] [rbp-238h] BYREF

  FilePart = 0;
  if ( !a1 || !a3 || !a2 )
  {
    v8 = 87;
    goto LABEL_19;
  }
  StringFromGUID2(a3, sz, 39);
  EnterCriticalSection(&g_CsJob);
  EnterCriticalSection(&g_CsQueue);
  for ( i = g_QueueListHead.Flink; i != &g_QueueListHead; i = i->Flink )
  {
    if ( LODWORD(i[2].Flink) == a1 )
      goto LABEL_9;
  }
  i = 0;
LABEL_9:
  LeaveCriticalSection(&g_CsQueue);
  LeaveCriticalSection(&g_CsJob);
  if ( !i
    || (*(_QWORD *)&a3->Data1 != *(_QWORD *)&gc_FaxSvcGuid.Data1
     || *(_QWORD *)a3->Data4 != *(_QWORD *)gc_FaxSvcGuid.Data4)
    && !FindRoutingMethodByGuid(sz) )
  {
    v8 = 13;
LABEL_19:
    SetLastError(v8);
    return 0xFFFFFFFFLL;
  }
  if ( GetFullPathNameW(a2, 0x104u, Buffer, &FilePart) )
  {
    v7 = pMemAlloc(0x28u);
    if ( v7 )
    {
      *(_QWORD *)(v7 + 16) = StringDup(Buffer);
      *(struct _GUID *)(v7 + 24) = *a3;
      EnterCriticalSection((LPCRITICAL_SECTION)&i[107].Blink);
      p_Flink = &i[106].Blink->Flink;
      *(_QWORD *)v7 = i + 106;
      *(_QWORD *)(v7 + 8) = p_Flink;
      *p_Flink = v7;
      i[106].Blink = (struct _LIST_ENTRY *)v7;
      LeaveCriticalSection((LPCRITICAL_SECTION)&i[107].Blink);
      EnterCriticalSection(&g_CsJob);
      EnterCriticalSection(&g_CsQueue);
      v10 = ++LODWORD(i[107].Flink);
      LeaveCriticalSection(&g_CsQueue);
      LeaveCriticalSection(&g_CsJob);
      return v10;
    }
    v8 = 8;
    goto LABEL_19;
  }
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x140042940  mov     [rsp+arg_0], rbx
0x140042945  push    rbp
0x140042946  push    rsi
0x140042947  push    rdi
0x140042948  sub     rsp, 2A0h
0x14004294f  mov     rax, cs:__security_cookie
0x140042956  xor     rax, rsp
0x140042959  mov     [rsp+2B8h+var_28], rax
0x140042961  mov     [rsp+2B8h+FilePart], 0
0x14004296a  mov     rbx, r8
0x14004296d  mov     rbp, rdx
0x140042970  mov     esi, ecx
0x140042972  test    ecx, ecx
0x140042974  jz      loc_140042AFB
0x14004297a  test    rbx, rbx
0x14004297d  jz      loc_140042AFB
0x140042983  test    rdx, rdx
0x140042986  jz      loc_140042AFB
0x14004298c  mov     r8d, 27h ; '''; cchMax
0x140042992  lea     rdx, [rsp+2B8h+sz]; lpsz
0x140042997  mov     rcx, rbx; rguid
0x14004299a  call    cs:__imp_StringFromGUID2
0x1400429a0  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400429a7  call    cs:__imp_EnterCriticalSection
0x1400429ad  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400429b4  call    cs:__imp_EnterCriticalSection
0x1400429ba  mov     rdi, cs:?g_QueueListHead@@3U_LIST_ENTRY@@A.Flink; _LIST_ENTRY g_QueueListHead ...
0x1400429c1  lea     rax, ?g_QueueListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_QueueListHead
0x1400429c8  jmp     short loc_1400429D2
0x1400429ca  cmp     [rdi+20h], esi
0x1400429cd  jz      short loc_1400429D9
0x1400429cf  mov     rdi, [rdi]
0x1400429d2  cmp     rdi, rax
0x1400429d5  jnz     short loc_1400429CA
0x1400429d7  xor     edi, edi
0x1400429d9  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400429e0  call    cs:__imp_LeaveCriticalSection
0x1400429e6  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400429ed  call    cs:__imp_LeaveCriticalSection
0x1400429f3  test    rdi, rdi
0x1400429f6  jz      loc_140042AF4
0x1400429fc  mov     rax, [rbx]
0x1400429ff  cmp     rax, qword ptr cs:?gc_FaxSvcGuid@@3U_GUID@@B.Data1; _GUID const gc_FaxSvcGuid ...
0x140042a06  jnz     short loc_140042A15
0x140042a08  mov     rax, [rbx+8]
0x140042a0c  cmp     rax, qword ptr cs:?gc_FaxSvcGuid@@3U_GUID@@B.Data4; _GUID const gc_FaxSvcGuid ...
0x140042a13  jz      short loc_140042A28
0x140042a15  lea     rcx, [rsp+2B8h+sz]; unsigned __int16 *
0x140042a1a  call    ?FindRoutingMethodByGuid@@YAPEAU_ROUTING_METHOD@@PEBG@Z; FindRoutingMethodByGuid(ushort const *)
0x140042a1f  test    rax, rax
0x140042a22  jz      loc_140042AF4
0x140042a28  lea     r9, [rsp+2B8h+FilePart]; lpFilePart
0x140042a2d  mov     edx, 104h; nBufferLength
0x140042a32  lea     r8, [rsp+2B8h+Buffer]; lpBuffer
0x140042a3a  mov     rcx, rbp; lpFileName
0x140042a3d  call    cs:__imp_GetFullPathNameW
0x140042a43  test    eax, eax
0x140042a45  jz      loc_140042B06
0x140042a4b  mov     ecx, 28h ; '('; dwBytes
0x140042a50  call    pMemAlloc
0x140042a55  mov     rsi, rax
0x140042a58  test    rax, rax
0x140042a5b  jnz     short loc_140042A65
0x140042a5d  lea     ecx, [rax+8]
0x140042a60  jmp     loc_140042B00
0x140042a65  lea     rcx, [rsp+2B8h+Buffer]; unsigned __int16 *
0x140042a6d  call    StringDup
0x140042a72  mov     [rsi+10h], rax
0x140042a76  movups  xmm0, xmmword ptr [rbx]
0x140042a79  lea     rbx, [rdi+6B8h]
0x140042a80  mov     rcx, rbx; lpCriticalSection
0x140042a83  movdqu  xmmword ptr [rsi+18h], xmm0
0x140042a88  call    cs:__imp_EnterCriticalSection
0x140042a8e  lea     rdx, [rdi+6A0h]
0x140042a95  mov     rcx, rbx; lpCriticalSection
0x140042a98  mov     rax, [rdx+8]
0x140042a9c  mov     [rsi], rdx
0x140042a9f  mov     [rsi+8], rax
0x140042aa3  mov     [rax], rsi
0x140042aa6  mov     [rdx+8], rsi
0x140042aaa  call    cs:__imp_LeaveCriticalSection
0x140042ab0  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140042ab7  call    cs:__imp_EnterCriticalSection
0x140042abd  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140042ac4  call    cs:__imp_EnterCriticalSection
0x140042aca  inc     dword ptr [rdi+6B0h]
0x140042ad0  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140042ad7  mov     ebx, [rdi+6B0h]
0x140042add  call    cs:__imp_LeaveCriticalSection
0x140042ae3  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140042aea  call    cs:__imp_LeaveCriticalSection
0x140042af0  mov     eax, ebx
0x140042af2  jmp     short loc_140042B09
0x140042af4  mov     ecx, 0Dh
0x140042af9  jmp     short loc_140042B00
0x140042afb  mov     ecx, 57h ; 'W'; dwErrCode
0x140042b00  call    cs:__imp_SetLastError
0x140042b06  or      eax, 0FFFFFFFFh
0x140042b09  mov     rcx, [rsp+2B8h+var_28]
0x140042b11  xor     rcx, rsp; StackCookie
0x140042b14  call    __security_check_cookie
0x140042b19  mov     rbx, [rsp+2B8h+arg_0]
0x140042b21  add     rsp, 2A0h
0x140042b28  pop     rdi
0x140042b29  pop     rsi
0x140042b2a  pop     rbp
0x140042b2b  retn
```
