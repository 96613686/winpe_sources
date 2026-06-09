# CBrowserBrokerInstance::BringIEToForeground(ulong,HWND__ *,int *)

- ea: `0x1800076b0`
- end: `0x18000778d`
- name: `?BringIEToForeground@CBrowserBrokerInstance@@UEAAJKPEAUHWND__@@PEAH@Z`
- size: `221`
- prototype: `__int64 __fastcall(CBrowserBrokerInstance *this, int, HWND, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800076b0`
- `0x18000e428`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetForegroundWindow` at `0x18000775f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetForegroundWindow` at `0x18000775f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!FindWindowExW` at `0x180007701`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!FindWindowExW` at `0x180007701`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18000771f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18000771f`

## pseudocode

```c
__int64 __fastcall CBrowserBrokerInstance::BringIEToForeground(CBrowserBrokerInstance *this, int a2, HWND a3, int *a4)
{
  __int64 result; // rax
  char v8; // di
  HWND v9; // rbx
  HWND v10; // rsi
  HWND Window; // rax
  DWORD dwProcessId[18]; // [rsp+20h] [rbp-48h] BYREF

  dwProcessId[0] = 0;
  result = BrokerAuthenticateAttachedCallerGetPIC(1, dwProcessId);
  if ( (int)result >= 0 )
  {
    v8 = 0;
    v9 = 0;
    v10 = 0;
    do
    {
      Window = FindWindowExW(0, v10, L"IEFrame", 0);
      v10 = Window;
      if ( !Window )
        break;
      dwProcessId[0] = 0;
      GetWindowThreadProcessId(Window, dwProcessId);
      if ( dwProcessId[0] && dwProcessId[0] == a2 )
      {
        if ( v9 )
          goto LABEL_14;
        if ( a3 == v10 || !a3 )
        {
          v9 = v10;
          if ( a3 )
            v8 = 1;
        }
      }
    }
    while ( !v8 );
    if ( v9 )
    {
      *a4 = 1;
      return !SetForegroundWindow(v9) ? 0x80004005 : 0;
    }
LABEL_14:
    result = 2147500037LL;
    *a4 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800076b0  push    rbx
0x1800076b2  push    rbp
0x1800076b3  push    rsi
0x1800076b4  push    rdi
0x1800076b5  push    r13
0x1800076b7  push    r14
0x1800076b9  push    r15
0x1800076bb  sub     rsp, 30h
0x1800076bf  mov     r15d, edx
0x1800076c2  mov     [rsp+68h+dwProcessId], 0
0x1800076ca  mov     r13d, 1
0x1800076d0  lea     rdx, [rsp+68h+dwProcessId]; unsigned int *
0x1800076d5  mov     ecx, r13d; unsigned int
0x1800076d8  mov     r14, r9
0x1800076db  mov     rbp, r8
0x1800076de  call    ?BrokerAuthenticateAttachedCallerGetPIC@@YAJKPEAK@Z; BrokerAuthenticateAttachedCallerGetPIC(ulong,ulong *)
0x1800076e3  test    eax, eax
0x1800076e5  js      loc_18000777E
0x1800076eb  xor     dil, dil
0x1800076ee  xor     ebx, ebx
0x1800076f0  xor     esi, esi
0x1800076f2  xor     r9d, r9d; lpszWindow
0x1800076f5  lea     r8, szClass; "IEFrame"
0x1800076fc  mov     rdx, rsi; hWndChildAfter
0x1800076ff  xor     ecx, ecx; hWndParent
0x180007701  call    cs:__imp_FindWindowExW
0x180007707  mov     rsi, rax
0x18000770a  test    rax, rax
0x18000770d  jz      short loc_180007754
0x18000770f  lea     rdx, [rsp+68h+dwProcessId]; lpdwProcessId
0x180007714  mov     [rsp+68h+dwProcessId], 0
0x18000771c  mov     rcx, rax; hWnd
0x18000771f  call    cs:__imp_GetWindowThreadProcessId
0x180007725  mov     eax, [rsp+68h+dwProcessId]
0x180007729  test    eax, eax
0x18000772b  jz      short loc_18000774F
0x18000772d  cmp     eax, r15d
0x180007730  jnz     short loc_18000774F
0x180007732  test    rbx, rbx
0x180007735  jnz     short loc_180007772
0x180007737  cmp     rbp, rsi
0x18000773a  jz      short loc_180007741
0x18000773c  test    rbp, rbp
0x18000773f  jnz     short loc_18000774F
0x180007741  test    rbp, rbp
0x180007744  movzx   edi, dil
0x180007748  mov     rbx, rsi
0x18000774b  cmovnz  edi, r13d
0x18000774f  test    dil, dil
0x180007752  jz      short loc_1800076F2
0x180007754  test    rbx, rbx
0x180007757  jz      short loc_180007772
0x180007759  mov     rcx, rbx; hWnd
0x18000775c  mov     [r14], r13d
0x18000775f  call    cs:__imp_SetForegroundWindow
0x180007765  neg     eax
0x180007767  sbb     eax, eax
0x180007769  not     eax
0x18000776b  and     eax, 80004005h
0x180007770  jmp     short loc_18000777E
0x180007772  mov     eax, 80004005h
0x180007777  mov     dword ptr [r14], 0
0x18000777e  add     rsp, 30h
0x180007782  pop     r15
0x180007784  pop     r14
0x180007786  pop     r13
0x180007788  pop     rdi
0x180007789  pop     rsi
0x18000778a  pop     rbp
0x18000778b  pop     rbx
0x18000778c  retn
```
