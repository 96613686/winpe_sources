# _CbsUninstallOSThreadProc(void *)

- ea: `0x18001dce0`
- end: `0x18001dd46`
- name: `?_CbsUninstallOSThreadProc@@YAKPEAX@Z`
- size: `102`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18001dce0`

## import_xrefs

- `USER32!PostMessageW` at `0x18001dd38`
- `USER32!PostMessageW` at `0x18001dd38`
- `ServicingCommon!UninstallWindows` at `0x18001dd05`
- `ServicingCommon!UninstallWindows` at `0x18001dd05`

## pseudocode

```c
__int64 __fastcall _CbsUninstallOSThreadProc(_DWORD *Parameter)
{
  int v2; // eax
  HWND v3; // rcx
  int v5; // [rsp+40h] [rbp+8h] BYREF

  v5 = 0;
  v2 = UninstallWindows(0, 0, 0, Parameter, &v5);
  Parameter[11] = v2;
  if ( v2 >= 0 )
    Parameter[142] = v5;
  v3 = (HWND)*((_QWORD *)Parameter + 73);
  if ( v3 )
    PostMessageW(v3, 0x466u, 1u, 0);
  return 1;
}

```

## disassembly

```asm
0x18001dce0  push    rbx
0x18001dce2  sub     rsp, 30h
0x18001dce6  mov     rbx, rcx
0x18001dce9  mov     [rsp+38h+arg_0], 0
0x18001dcf1  lea     rax, [rsp+38h+arg_0]
0x18001dcf6  mov     r9, rcx
0x18001dcf9  xor     ecx, ecx
0x18001dcfb  mov     [rsp+38h+var_18], rax
0x18001dd00  xor     r8d, r8d
0x18001dd03  xor     edx, edx
0x18001dd05  call    cs:__imp_UninstallWindows
0x18001dd0b  mov     [rbx+2Ch], eax
0x18001dd0e  test    eax, eax
0x18001dd10  js      short loc_18001DD1C
0x18001dd12  mov     eax, [rsp+38h+arg_0]
0x18001dd16  mov     [rbx+238h], eax
0x18001dd1c  mov     rcx, [rbx+248h]; hWnd
0x18001dd23  mov     ebx, 1
0x18001dd28  test    rcx, rcx
0x18001dd2b  jz      short loc_18001DD3E
0x18001dd2d  xor     r9d, r9d; lParam
0x18001dd30  mov     r8d, ebx; wParam
0x18001dd33  mov     edx, 466h; Msg
0x18001dd38  call    cs:__imp_PostMessageW
0x18001dd3e  mov     eax, ebx
0x18001dd40  add     rsp, 30h
0x18001dd44  pop     rbx
0x18001dd45  retn
```
