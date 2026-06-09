# CxsStartWlanNotification(_GIP_WLAN_CLIENT *)

- ea: `0x18000a36c`
- end: `0x18000a448`
- name: `?CxsStartWlanNotification@@YAKPEAU_GIP_WLAN_CLIENT@@@Z`
- size: `220`
- prototype: `__int64 __fastcall(struct _GIP_WLAN_CLIENT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000aa40`

## callees

- `0x1800016c0`
- `0x180002b70`
- `0x18000a36c`
- `0x18000a9c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a3c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a3c4`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18000a3ba`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18000a3ba`

## pseudocode

```c
__int64 __fastcall CxsStartWlanNotification(struct _GIP_WLAN_CLIENT *a1)
{
  SC_HANDLE v2; // rcx
  DWORD LastError; // ebx
  DWORD pcbBytesNeeded; // [rsp+30h] [rbp-48h] BYREF
  BYTE Buffer[16]; // [rsp+38h] [rbp-40h] BYREF
  __int128 v7; // [rsp+48h] [rbp-30h]
  int v8; // [rsp+58h] [rbp-20h]

  pcbBytesNeeded = 0;
  v8 = 0;
  v2 = (SC_HANDLE)*((_QWORD *)a1 + 9);
  *(_OWORD *)Buffer = 0;
  v7 = 0;
  if ( QueryServiceStatusEx(v2, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
  {
    *((_QWORD *)a1 + 13) = a1;
    *((_QWORD *)a1 + 12) = CxsWlanServiceNotification;
    *((_DWORD *)a1 + 30) = *(_DWORD *)&Buffer[4];
    *((_DWORD *)a1 + 22) = 2;
    *((_DWORD *)a1 + 28) = 0;
    CxsWlanServiceNotification((char *)a1 + 88);
    return 0;
  }
  else
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_4b7fc9b143d0368172f607d8a9267014_Traceguids, LastError);
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x18000a36c  push    rbx
0x18000a36e  sub     rsp, 70h
0x18000a372  mov     rax, cs:__security_cookie
0x18000a379  xor     rax, rsp
0x18000a37c  mov     [rsp+78h+var_18], rax
0x18000a381  xor     eax, eax
0x18000a383  mov     [rsp+78h+var_48], 0
0x18000a38b  xorps   xmm0, xmm0
0x18000a38e  mov     [rsp+78h+var_20], eax
0x18000a392  lea     rax, [rsp+78h+var_48]
0x18000a397  mov     rbx, rcx
0x18000a39a  mov     rcx, [rcx+48h]; hService
0x18000a39e  lea     r8, [rsp+78h+Buffer]; lpBuffer
0x18000a3a3  mov     r9d, 24h ; '$'; cbBufSize
0x18000a3a9  mov     [rsp+78h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18000a3ae  xor     edx, edx; InfoLevel
0x18000a3b0  movups  xmmword ptr [rsp+78h+Buffer], xmm0
0x18000a3b5  movups  [rsp+78h+var_30], xmm0
0x18000a3ba  call    cs:__imp_QueryServiceStatusEx
0x18000a3c0  test    eax, eax
0x18000a3c2  jnz     short loc_18000A405
0x18000a3c4  call    cs:__imp_GetLastError
0x18000a3ca  mov     ebx, eax
0x18000a3cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a3d3  lea     rax, WPP_GLOBAL_Control
0x18000a3da  cmp     rcx, rax
0x18000a3dd  jz      short loc_18000A433
0x18000a3df  test    byte ptr [rcx+1Ch], 4
0x18000a3e3  jz      short loc_18000A433
0x18000a3e5  cmp     byte ptr [rcx+19h], 1
0x18000a3e9  jb      short loc_18000A433
0x18000a3eb  mov     rcx, [rcx+10h]
0x18000a3ef  lea     r8, WPP_4b7fc9b143d0368172f607d8a9267014_Traceguids
0x18000a3f6  mov     edx, 23h ; '#'
0x18000a3fb  mov     r9d, ebx
0x18000a3fe  call    WPP_SF_D
0x18000a403  jmp     short loc_18000A433
0x18000a405  lea     rax, ?CxsWlanServiceNotification@@YAXPEAX@Z; CxsWlanServiceNotification(void *)
0x18000a40c  mov     [rbx+68h], rbx
0x18000a410  mov     [rbx+60h], rax
0x18000a414  lea     rcx, [rbx+58h]; void *
0x18000a418  mov     eax, dword ptr [rsp+78h+Buffer+4]
0x18000a41c  mov     [rbx+78h], eax
0x18000a41f  mov     dword ptr [rcx], 2
0x18000a425  mov     dword ptr [rbx+70h], 0
0x18000a42c  call    ?CxsWlanServiceNotification@@YAXPEAX@Z; CxsWlanServiceNotification(void *)
0x18000a431  xor     ebx, ebx
0x18000a433  mov     eax, ebx
0x18000a435  mov     rcx, [rsp+78h+var_18]
0x18000a43a  xor     rcx, rsp; StackCookie
0x18000a43d  call    __security_check_cookie
0x18000a442  add     rsp, 70h
0x18000a446  pop     rbx
0x18000a447  retn
```
