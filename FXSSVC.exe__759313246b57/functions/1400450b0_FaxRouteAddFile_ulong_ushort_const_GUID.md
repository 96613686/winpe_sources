# FaxRouteAddFile(ulong,ushort const *,_GUID *)

- ea: `0x1400450b0`
- end: `0x1400452eb`
- name: `?FaxRouteAddFile@@YAJKPEBGPEAU_GUID@@@Z`
- size: `571`
- prototype: `int(unsigned int, const unsigned __int16 *, struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140044ad8`

## callees

- `0x1400450b0`
- `0x140045cec`
- `0x1400698ec`
- `0x14006af2c`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1400452b8`
- `KERNEL32!SetLastError` at `0x1400452b8`
- `KERNEL32!EnterCriticalSection` at `0x14004511d`
- `KERNEL32!EnterCriticalSection` at `0x140045130`
- `KERNEL32!EnterCriticalSection` at `0x14004521c`
- `KERNEL32!EnterCriticalSection` at `0x140045257`
- `KERNEL32!EnterCriticalSection` at `0x14004526a`
- `KERNEL32!EnterCriticalSection` at `0x14004511d`
- `KERNEL32!EnterCriticalSection` at `0x140045130`
- `KERNEL32!EnterCriticalSection` at `0x14004521c`
- `KERNEL32!EnterCriticalSection` at `0x140045257`
- `KERNEL32!EnterCriticalSection` at `0x14004526a`
- `KERNEL32!LeaveCriticalSection` at `0x140045162`
- `KERNEL32!LeaveCriticalSection` at `0x140045175`
- `KERNEL32!LeaveCriticalSection` at `0x140045244`
- `KERNEL32!LeaveCriticalSection` at `0x140045289`
- `KERNEL32!LeaveCriticalSection` at `0x14004529c`
- `KERNEL32!LeaveCriticalSection` at `0x140045162`
- `KERNEL32!LeaveCriticalSection` at `0x140045175`
- `KERNEL32!LeaveCriticalSection` at `0x140045244`
- `KERNEL32!LeaveCriticalSection` at `0x140045289`
- `KERNEL32!LeaveCriticalSection` at `0x14004529c`
- `KERNEL32!GetFullPathNameW` at `0x1400451cb`
- `KERNEL32!GetFullPathNameW` at `0x1400451cb`
- `ole32!StringFromGUID2` at `0x14004510a`
- `ole32!StringFromGUID2` at `0x14004510a`

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
0x1400450b0  mov     [rsp+arg_0], rbx
0x1400450b5  push    rbp
0x1400450b6  push    rsi
0x1400450b7  push    rdi
0x1400450b8  sub     rsp, 2A0h
0x1400450bf  mov     rax, cs:__security_cookie
0x1400450c6  xor     rax, rsp
0x1400450c9  mov     [rsp+2B8h+var_28], rax
0x1400450d1  mov     [rsp+2B8h+FilePart], 0
0x1400450da  mov     rbx, r8
0x1400450dd  mov     rbp, rdx
0x1400450e0  mov     esi, ecx
0x1400450e2  test    ecx, ecx
0x1400450e4  jz      loc_1400452B3
0x1400450ea  test    rbx, rbx
0x1400450ed  jz      loc_1400452B3
0x1400450f3  test    rdx, rdx
0x1400450f6  jz      loc_1400452B3
0x1400450fc  mov     r8d, 27h ; '''; cchMax
0x140045102  lea     rdx, [rsp+2B8h+sz]; lpsz
0x140045107  mov     rcx, rbx; rguid
0x14004510a  call    cs:__imp_StringFromGUID2
0x140045111  nop     dword ptr [rax+rax+00h]
0x140045116  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14004511d  call    cs:__imp_EnterCriticalSection
0x140045124  nop     dword ptr [rax+rax+00h]
0x140045129  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140045130  call    cs:__imp_EnterCriticalSection
0x140045137  nop     dword ptr [rax+rax+00h]
0x14004513c  mov     rdi, cs:?g_QueueListHead@@3U_LIST_ENTRY@@A.Flink; _LIST_ENTRY g_QueueListHead ...
0x140045143  lea     rax, ?g_QueueListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_QueueListHead
0x14004514a  jmp     short loc_140045154
0x14004514c  cmp     [rdi+20h], esi
0x14004514f  jz      short loc_14004515B
0x140045151  mov     rdi, [rdi]
0x140045154  cmp     rdi, rax
0x140045157  jnz     short loc_14004514C
0x140045159  xor     edi, edi
0x14004515b  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140045162  call    cs:__imp_LeaveCriticalSection
0x140045169  nop     dword ptr [rax+rax+00h]
0x14004516e  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140045175  call    cs:__imp_LeaveCriticalSection
0x14004517c  nop     dword ptr [rax+rax+00h]
0x140045181  test    rdi, rdi
0x140045184  jz      loc_1400452AC
0x14004518a  mov     rax, [rbx]
0x14004518d  cmp     rax, qword ptr cs:?gc_FaxSvcGuid@@3U_GUID@@B.Data1; _GUID const gc_FaxSvcGuid ...
0x140045194  jnz     short loc_1400451A3
0x140045196  mov     rax, [rbx+8]
0x14004519a  cmp     rax, qword ptr cs:?gc_FaxSvcGuid@@3U_GUID@@B.Data4; _GUID const gc_FaxSvcGuid ...
0x1400451a1  jz      short loc_1400451B6
0x1400451a3  lea     rcx, [rsp+2B8h+sz]; unsigned __int16 *
0x1400451a8  call    ?FindRoutingMethodByGuid@@YAPEAU_ROUTING_METHOD@@PEBG@Z; FindRoutingMethodByGuid(ushort const *)
0x1400451ad  test    rax, rax
0x1400451b0  jz      loc_1400452AC
0x1400451b6  lea     r9, [rsp+2B8h+FilePart]; lpFilePart
0x1400451bb  mov     edx, 104h; nBufferLength
0x1400451c0  lea     r8, [rsp+2B8h+Buffer]; lpBuffer
0x1400451c8  mov     rcx, rbp; lpFileName
0x1400451cb  call    cs:__imp_GetFullPathNameW
0x1400451d2  nop     dword ptr [rax+rax+00h]
0x1400451d7  test    eax, eax
0x1400451d9  jz      loc_1400452C4
0x1400451df  mov     ecx, 28h ; '('; dwBytes
0x1400451e4  call    pMemAlloc
0x1400451e9  mov     rsi, rax
0x1400451ec  test    rax, rax
0x1400451ef  jnz     short loc_1400451F9
0x1400451f1  lea     ecx, [rax+8]
0x1400451f4  jmp     loc_1400452B8
0x1400451f9  lea     rcx, [rsp+2B8h+Buffer]; unsigned __int16 *
0x140045201  call    StringDup
0x140045206  mov     [rsi+10h], rax
0x14004520a  movups  xmm0, xmmword ptr [rbx]
0x14004520d  lea     rbx, [rdi+6B8h]
0x140045214  mov     rcx, rbx; lpCriticalSection
0x140045217  movdqu  xmmword ptr [rsi+18h], xmm0
0x14004521c  call    cs:__imp_EnterCriticalSection
0x140045223  nop     dword ptr [rax+rax+00h]
0x140045228  lea     rdx, [rdi+6A0h]
0x14004522f  mov     rcx, rbx; lpCriticalSection
0x140045232  mov     rax, [rdx+8]
0x140045236  mov     [rsi], rdx
0x140045239  mov     [rsi+8], rax
0x14004523d  mov     [rax], rsi
0x140045240  mov     [rdx+8], rsi
0x140045244  call    cs:__imp_LeaveCriticalSection
0x14004524b  nop     dword ptr [rax+rax+00h]
0x140045250  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140045257  call    cs:__imp_EnterCriticalSection
0x14004525e  nop     dword ptr [rax+rax+00h]
0x140045263  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14004526a  call    cs:__imp_EnterCriticalSection
0x140045271  nop     dword ptr [rax+rax+00h]
0x140045276  inc     dword ptr [rdi+6B0h]
0x14004527c  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140045283  mov     ebx, [rdi+6B0h]
0x140045289  call    cs:__imp_LeaveCriticalSection
0x140045290  nop     dword ptr [rax+rax+00h]
0x140045295  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14004529c  call    cs:__imp_LeaveCriticalSection
0x1400452a3  nop     dword ptr [rax+rax+00h]
0x1400452a8  mov     eax, ebx
0x1400452aa  jmp     short loc_1400452C7
0x1400452ac  mov     ecx, 0Dh
0x1400452b1  jmp     short loc_1400452B8
0x1400452b3  mov     ecx, 57h ; 'W'; dwErrCode
0x1400452b8  call    cs:__imp_SetLastError
0x1400452bf  nop     dword ptr [rax+rax+00h]
0x1400452c4  or      eax, 0FFFFFFFFh
0x1400452c7  mov     rcx, [rsp+2B8h+var_28]
0x1400452cf  xor     rcx, rsp; StackCookie
0x1400452d2  call    __security_check_cookie
0x1400452d7  mov     rbx, [rsp+2B8h+arg_0]
0x1400452df  add     rsp, 2A0h
0x1400452e6  pop     rdi
0x1400452e7  pop     rsi
0x1400452e8  pop     rbp
0x1400452e9  retn
```
