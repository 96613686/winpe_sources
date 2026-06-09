# CPimcManager::HookProc(int,unsigned __int64,__int64)

- ea: `0x18000b5d0`
- end: `0x18000b6b5`
- name: `?HookProc@CPimcManager@@SA_JH_K_J@Z`
- size: `229`
- prototype: `LRESULT __stdcall(int code, WPARAM wParam, LPARAM lParam)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, installer_update`

## callees

- `0x18000b5d0`
- `0x18000b834`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x18000b617`
- `KERNEL32!GetCurrentProcessId` at `0x18000b617`
- `USER32!CallNextHookEx` at `0x18000b6a3`
- `USER32!CallNextHookEx` at `0x18000b6a3`
- `USER32!GetWindowThreadProcessId` at `0x18000b60f`
- `USER32!GetWindowThreadProcessId` at `0x18000b60f`
- `USER32!IsWindow` at `0x18000b5f9`
- `USER32!IsWindow` at `0x18000b5f9`

## pseudocode

```c
LRESULT __fastcall CPimcManager::HookProc(int code, WPARAM wParam, LPARAM lParam)
{
  LPARAM v3; // rbx
  WPARAM v4; // r15
  int v5; // r14d
  HWND v6; // rdi
  DWORD WindowThreadProcessId; // esi
  unsigned int v8; // edx
  HWND v9; // r8
  DWORD dwProcessId; // [rsp+68h] [rbp+20h] BYREF

  v3 = lParam;
  v4 = wParam;
  v5 = code;
  v6 = *(HWND *)(lParam + 24);
  if ( !IsWindow(v6) )
    return CallNextHookEx(0, v5, v4, v3);
  WindowThreadProcessId = GetWindowThreadProcessId(v6, &dwProcessId);
  if ( GetCurrentProcessId() != dwProcessId )
    return CallNextHookEx(0, v5, v4, v3);
  try
  {
    if ( v5 >= 0 )
    {
      if ( *(_DWORD *)(v3 + 16) == 3 || (v8 = 2, *(_DWORD *)(v3 + 16) == 5) )
      {
        v8 = 1;
      }
      else if ( *(_DWORD *)(v3 + 16) == 6 )
      {
        if ( !*(_QWORD *)(v3 + 8) )
          return CallNextHookEx(0, v5, v4, v3);
      }
      else if ( *(_DWORD *)(v3 + 16) != 34 )
      {
        switch ( *(_DWORD *)(v3 + 16) )
        {
          case 0x111:
            if ( *(_WORD *)(v3 + 10) != 8 )
              return CallNextHookEx(0, v5, v4, v3);
            break;
          case 0x125:
            break;
          case 0x222:
            v9 = *(HWND *)v3;
            goto LABEL_19;
          default:
            return CallNextHookEx(0, v5, v4, v3);
        }
      }
      v9 = v6;
LABEL_19:
      CPimcManager::MgrHandleCtxUpdate(WindowThreadProcessId, v8, v9);
    }
  }
  catch ( ... )
  {
    v3 = lParam;
    v4 = wParam;
    v5 = code;
  }
  return CallNextHookEx(0, v5, v4, v3);
}

```

## disassembly

```asm
0x18000b5d0  mov     [rsp+arg_10], r8
0x18000b5d5  mov     [rsp+arg_8], rdx
0x18000b5da  mov     [rsp+arg_0], ecx
0x18000b5de  push    rbx
0x18000b5df  push    rsi
0x18000b5e0  push    rdi
0x18000b5e1  push    r14
0x18000b5e3  push    r15
0x18000b5e5  sub     rsp, 20h
0x18000b5e9  mov     rbx, r8
0x18000b5ec  mov     r15, rdx
0x18000b5ef  mov     r14d, ecx
0x18000b5f2  mov     rdi, [r8+18h]
0x18000b5f6  mov     rcx, rdi; hWnd
0x18000b5f9  call    cs:__imp_IsWindow
0x18000b5ff  test    eax, eax
0x18000b601  jz      loc_18000B698
0x18000b607  lea     rdx, [rsp+48h+dwProcessId]; lpdwProcessId
0x18000b60c  mov     rcx, rdi; hWnd
0x18000b60f  call    cs:__imp_GetWindowThreadProcessId
0x18000b615  mov     esi, eax
0x18000b617  call    cs:__imp_GetCurrentProcessId
0x18000b61d  cmp     eax, [rsp+48h+dwProcessId]
0x18000b621  jnz     short loc_18000B698
0x18000b623  test    r14d, r14d
0x18000b626  js      short loc_18000B687
0x18000b628  mov     r8d, [rbx+10h]
0x18000b62c  sub     r8d, 3
0x18000b630  jz      short loc_18000B677
0x18000b632  mov     edx, 2
0x18000b637  sub     r8d, edx
0x18000b63a  jz      short loc_18000B677
0x18000b63c  sub     r8d, 1
0x18000b640  jz      short loc_18000B66E
0x18000b642  sub     r8d, 1Ch
0x18000b646  jz      short loc_18000B67C
0x18000b648  sub     r8d, 0EFh
0x18000b64f  jz      short loc_18000B665
0x18000b651  sub     r8d, 14h
0x18000b655  jz      short loc_18000B67C
0x18000b657  cmp     r8d, 0FDh
0x18000b65e  jnz     short loc_18000B687
0x18000b660  mov     r8, [rbx]
0x18000b663  jmp     short loc_18000B67F
0x18000b665  cmp     word ptr [rbx+0Ah], 8
0x18000b66a  jnz     short loc_18000B687
0x18000b66c  jmp     short loc_18000B67C
0x18000b66e  cmp     qword ptr [rbx+8], 0
0x18000b673  jz      short loc_18000B687
0x18000b675  jmp     short loc_18000B67C
0x18000b677  mov     edx, 1; unsigned int
0x18000b67c  mov     r8, rdi; HWND
0x18000b67f  mov     ecx, esi; unsigned int
0x18000b681  call    ?MgrHandleCtxUpdate@CPimcManager@@SAXKKPEAUHWND__@@@Z; CPimcManager::MgrHandleCtxUpdate(ulong,ulong,HWND__ *)
0x18000b686  nop
0x18000b687  jmp     short loc_18000B698
0x18000b689  mov     rbx, [rsp+48h+arg_10]
0x18000b68e  mov     r15, [rsp+48h+arg_8]
0x18000b693  mov     r14d, [rsp+48h+arg_0]
0x18000b698  mov     r9, rbx; lParam
0x18000b69b  mov     r8, r15; wParam
0x18000b69e  mov     edx, r14d; nCode
0x18000b6a1  xor     ecx, ecx; hhk
0x18000b6a3  call    cs:__imp_CallNextHookEx
0x18000b6a9  add     rsp, 20h
0x18000b6ad  pop     r15
0x18000b6af  pop     r14
0x18000b6b1  pop     rdi
0x18000b6b2  pop     rsi
0x18000b6b3  pop     rbx
0x18000b6b4  retn
```
