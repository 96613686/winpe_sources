# AuthHostWebInstance::Navigate(void)

- ea: `0x1400055d0`
- end: `0x140005740`
- name: `?Navigate@AuthHostWebInstance@@QEAAJXZ`
- size: `368`
- prototype: `__int64 __fastcall(AuthHostWebInstance *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140005940`

## callees

- `0x140002c70`
- `0x140002c98`
- `0x1400055d0`
- `0x1400067a0`
- `0x140009b84`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400056a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400056b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400056a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400056b2`
- `ext-ms-win-ntuser-draw-l1-1-0!UpdateWindow` at `0x14000572e`
- `ext-ms-win-ntuser-draw-l1-1-0!UpdateWindow` at `0x14000572e`
- `ext-ms-win-ntuser-window-l1-1-0!ShowWindow` at `0x140005724`
- `ext-ms-win-ntuser-window-l1-1-0!ShowWindow` at `0x140005724`

## pseudocode

```c
__int64 __fastcall AuthHostWebInstance::Navigate(AuthHostWebInstance *this)
{
  int v2; // eax
  int v3; // esi
  __int64 v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r9
  PCWSTR StringRawBuffer; // rbx
  PCWSTR v8; // rax
  __int64 v9; // rcx
  int v10; // edx

  v2 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 13) + 56LL))(
         *((_QWORD *)this + 13),
         (char *)this + 112);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v3 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 13) + 48LL))(
           *((_QWORD *)this + 13),
           (char *)this + 120);
    if ( v3 >= 0 )
    {
      if ( (Microsoft_Windows_WebAuthEnableBits & 1) != 0 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)this + 14), 0);
        v8 = WindowsGetStringRawBuffer(*((HSTRING *)this + 15), 0);
        McTemplateU0zz_EventWriteTransfer(v9, StartNavigateEvent, v8, StringRawBuffer);
      }
      AuthHostWebInstance::NavigateToAuthHostPage(this, 1);
      if ( (*((_DWORD *)this + 32) & 0x20000) != 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 44, &WPP_0796d3d6e744321e50f715e8d649e99c_Traceguids);
        }
        v10 = 0;
      }
      else
      {
        v10 = 1;
      }
      ShowWindow(*((HWND *)this + 8), v10);
      UpdateWindow(*((HWND *)this + 8));
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      v4 = *((_QWORD *)WPP_GLOBAL_Control + 7);
      v5 = 43;
      v6 = (unsigned int)v3;
      goto LABEL_6;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
  {
    v4 = *((_QWORD *)WPP_GLOBAL_Control + 7);
    v5 = 42;
    v6 = (unsigned int)v2;
LABEL_6:
    WPP_SF_d(v4, v5, &WPP_0796d3d6e744321e50f715e8d649e99c_Traceguids, v6);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1400055d0  push    rbx
0x1400055d2  push    rsi
0x1400055d3  push    rdi
0x1400055d4  push    r14
0x1400055d6  sub     rsp, 28h
0x1400055da  mov     rdi, rcx
0x1400055dd  mov     rcx, [rcx+68h]
0x1400055e1  mov     rax, [rcx]
0x1400055e4  lea     rdx, [rdi+70h]
0x1400055e8  mov     rax, [rax+38h]
0x1400055ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400055f1  mov     esi, eax
0x1400055f3  test    eax, eax
0x1400055f5  jns     short loc_140005641
0x1400055f7  mov     r10, cs:WPP_GLOBAL_Control
0x1400055fe  lea     rcx, WPP_GLOBAL_Control
0x140005605  cmp     r10, rcx
0x140005608  jz      loc_140005734
0x14000560e  test    byte ptr [r10+44h], 2
0x140005613  jz      loc_140005734
0x140005619  cmp     byte ptr [r10+41h], 2
0x14000561e  jb      loc_140005734
0x140005624  mov     rcx, [r10+38h]
0x140005628  mov     edx, 2Ah ; '*'
0x14000562d  mov     r9d, eax
0x140005630  lea     r8, WPP_0796d3d6e744321e50f715e8d649e99c_Traceguids
0x140005637  call    WPP_SF_d
0x14000563c  jmp     loc_140005734
0x140005641  mov     rcx, [rdi+68h]
0x140005645  lea     rdx, [rdi+78h]
0x140005649  mov     rax, [rcx]
0x14000564c  mov     rax, [rax+30h]
0x140005650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005655  mov     esi, eax
0x140005657  test    eax, eax
0x140005659  jns     short loc_140005694
0x14000565b  mov     rax, cs:WPP_GLOBAL_Control
0x140005662  lea     rcx, WPP_GLOBAL_Control
0x140005669  cmp     rax, rcx
0x14000566c  jz      loc_140005734
0x140005672  test    byte ptr [rax+44h], 2
0x140005676  jz      loc_140005734
0x14000567c  cmp     byte ptr [rax+41h], 2
0x140005680  jb      loc_140005734
0x140005686  mov     rcx, [rax+38h]
0x14000568a  mov     edx, 2Bh ; '+'
0x14000568f  mov     r9d, esi
0x140005692  jmp     short loc_140005630
0x140005694  test    cs:Microsoft_Windows_WebAuthEnableBits, 1
0x14000569b  jz      short loc_1400056CA
0x14000569d  mov     rcx, [rdi+70h]; string
0x1400056a1  xor     edx, edx; length
0x1400056a3  call    cs:__imp_WindowsGetStringRawBuffer
0x1400056a9  mov     rcx, [rdi+78h]; string
0x1400056ad  xor     edx, edx; length
0x1400056af  mov     rbx, rax
0x1400056b2  call    cs:__imp_WindowsGetStringRawBuffer
0x1400056b8  mov     r9, rbx
0x1400056bb  lea     rdx, StartNavigateEvent
0x1400056c2  mov     r8, rax
0x1400056c5  call    McTemplateU0zz_EventWriteTransfer
0x1400056ca  mov     edx, 1
0x1400056cf  mov     rcx, rdi
0x1400056d2  call    ?NavigateToAuthHostPage@AuthHostWebInstance@@AEAAXW4AuthHostPageState@1@@Z; AuthHostWebInstance::NavigateToAuthHostPage(AuthHostWebInstance::AuthHostPageState)
0x1400056d7  test    dword ptr [rdi+80h], 20000h
0x1400056e1  jz      short loc_14000571B
0x1400056e3  mov     rax, cs:WPP_GLOBAL_Control
0x1400056ea  lea     rcx, WPP_GLOBAL_Control
0x1400056f1  cmp     rax, rcx
0x1400056f4  jz      short loc_140005717
0x1400056f6  test    byte ptr [rax+44h], 2
0x1400056fa  jz      short loc_140005717
0x1400056fc  cmp     byte ptr [rax+41h], 5
0x140005700  jb      short loc_140005717
0x140005702  mov     rcx, [rax+38h]
0x140005706  lea     r8, WPP_0796d3d6e744321e50f715e8d649e99c_Traceguids
0x14000570d  mov     edx, 2Ch ; ','
0x140005712  call    WPP_SF_
0x140005717  xor     edx, edx
0x140005719  jmp     short loc_140005720
0x14000571b  mov     edx, 1; nCmdShow
0x140005720  mov     rcx, [rdi+40h]; hWnd
0x140005724  call    cs:__imp_ShowWindow
0x14000572a  mov     rcx, [rdi+40h]; hWnd
0x14000572e  call    cs:__imp_UpdateWindow
0x140005734  mov     eax, esi
0x140005736  add     rsp, 28h
0x14000573a  pop     r14
0x14000573c  pop     rdi
0x14000573d  pop     rsi
0x14000573e  pop     rbx
0x14000573f  retn
```
