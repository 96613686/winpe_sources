# _LaunchUIThreadProc

- ea: `0x18001ddb0`
- end: `0x18001de74`
- name: `_LaunchUIThreadProc`
- size: `196`
- prototype: `unsigned int __fastcall(void *lpThreadParameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000737c`
- `0x18001dc20`
- `0x18001ddb0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001de19`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001de19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001de66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001de66`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001de27`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001de27`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001ddc0`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001ddc0`

## pseudocode

```c
__int64 __fastcall LaunchUIThreadProc(wchar_t *lpThreadParameter)
{
  HRESULT v2; // r9d

  v2 = CoInitializeEx(0, 6u);
  if ( v2 < 0 )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 2) != 0
      && WPP_GLOBAL_Control[1].Control.Level >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Control.Logger, 0xEu, WPP_5c25b29c16823e432c896bdd05006b28_Traceguids, v2);
    }
  }
  else
  {
    if ( (unsigned int)DoLaunchUI(lpThreadParameter) == -2147023893 )
    {
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 2) != 0
        && WPP_GLOBAL_Control[1].Control.Level >= 2u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control[1].Control.Logger,
          0xDu,
          WPP_5c25b29c16823e432c896bdd05006b28_Traceguids,
          0x800703EB);
      }
      Sleep(0x64u);
      DoLaunchUI(lpThreadParameter);
    }
    CoUninitialize();
  }
  CoTaskMemFree(lpThreadParameter);
  return 0;
}

```

## disassembly

```asm
0x18001ddb0  push    rbx
0x18001ddb2  sub     rsp, 20h
0x18001ddb6  mov     rbx, lpThreadParameter
0x18001ddb9  mov     edx, 6; dwCoInit
0x18001ddbe  xor     ecx, ecx; pvReserved
0x18001ddc0  call    cs:__imp_CoInitializeEx
0x18001ddc6  mov     r9d, eax; _a1
0x18001ddc9  test    eax, eax
0x18001ddcb  js      short loc_18001DE2F
0x18001ddcd  mov     lpThreadParameter, rbx; url
0x18001ddd0  call    _DoLaunchUI
0x18001ddd5  mov     r9d, 800703EBh; _a1
0x18001dddb  cmp     eax, r9d
0x18001ddde  jnz     short loc_18001DE27
0x18001dde0  mov     lpThreadParameter, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18001dde7  lea     rax, WPP_GLOBAL_Control
0x18001ddee  cmp     lpThreadParameter, rax
0x18001ddf1  jz      short loc_18001DE14
0x18001ddf3  test    byte ptr [lpThreadParameter+44h], 2
0x18001ddf7  jz      short loc_18001DE14
0x18001ddf9  cmp     byte ptr [lpThreadParameter+41h], 2
0x18001ddfd  jb      short loc_18001DE14
0x18001ddff  mov     lpThreadParameter, [lpThreadParameter+38h]; Logger
0x18001de03  lea     r8, WPP_5c25b29c16823e432c896bdd05006b28_Traceguids; TraceGuid
0x18001de0a  mov     edx, 0Dh; id
0x18001de0f  call    WPP_SF_d
0x18001de14  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18001de19  call    cs:__imp_Sleep
0x18001de1f  mov     lpThreadParameter, rbx; url
0x18001de22  call    _DoLaunchUI
0x18001de27  call    cs:__imp_CoUninitialize
0x18001de2d  jmp     short loc_18001DE63
0x18001de2f  mov     lpThreadParameter, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18001de36  lea     rax, WPP_GLOBAL_Control
0x18001de3d  cmp     lpThreadParameter, rax
0x18001de40  jz      short loc_18001DE63
0x18001de42  test    byte ptr [lpThreadParameter+44h], 2
0x18001de46  jz      short loc_18001DE63
0x18001de48  cmp     byte ptr [lpThreadParameter+41h], 2
0x18001de4c  jb      short loc_18001DE63
0x18001de4e  mov     lpThreadParameter, [lpThreadParameter+38h]; Logger
0x18001de52  lea     r8, WPP_5c25b29c16823e432c896bdd05006b28_Traceguids; TraceGuid
0x18001de59  mov     edx, 0Eh; id
0x18001de5e  call    WPP_SF_d
0x18001de63  mov     lpThreadParameter, rbx; pv
0x18001de66  call    cs:__imp_CoTaskMemFree
0x18001de6c  xor     eax, eax
0x18001de6e  add     rsp, 20h
0x18001de72  pop     rbx
0x18001de73  retn
```
