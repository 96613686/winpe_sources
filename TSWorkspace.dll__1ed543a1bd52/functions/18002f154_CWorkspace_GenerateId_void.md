# CWorkspace::GenerateId(void)

- ea: `0x18002f154`
- end: `0x18002f280`
- name: `?GenerateId@CWorkspace@@QEAAJXZ`
- size: `300`
- prototype: `__int64 __fastcall(GUID *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18004d994`

## callees

- `0x18000b1d8`
- `0x18000dbdc`
- `0x18000ece0`
- `0x18002f154`
- `0x18009a520`

## import_xrefs

- `ole32!StringFromGUID2` at `0x18002f244`
- `ole32!StringFromGUID2` at `0x18002f244`
- `ole32!CoCreateGuid` at `0x18002f1f4`
- `ole32!CoCreateGuid` at `0x18002f1f4`

## string_xrefs

- `0x18002f1c5`: `Attempting to overwrite Workspace Id`
- `0x18002f22d`: `CoCreateGuid failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall CWorkspace::GenerateId(GUID *this)
{
  GUID *v1; // rdi
  HRESULT Guid; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  const GUID *v4; // rsi
  unsigned int v5; // eax
  int v7; // [rsp+28h] [rbp-90h]
  HRESULT v8; // [rsp+28h] [rbp-90h]
  OLECHAR sz[56]; // [rsp+30h] [rbp-88h] BYREF

  v1 = this + 4;
  if ( *(_QWORD *)&this[5].Data1 )
  {
    Guid = -2147467259;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v7 = -2147467259;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        89,
        (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"Attempting to overwrite Workspace Id",
        v7);
    }
  }
  else
  {
    v4 = this + 3;
    Guid = CoCreateGuid(this + 3);
    if ( Guid >= 0 )
    {
      StringFromGUID2(v4, sz, 50);
      std::wstring::assign(v1, sz);
      return 0;
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = RdpWppGetCurrentThreadActivityIdPrefix();
      v8 = Guid;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        90,
        (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
        v5,
        (__int64)"CoCreateGuid failed",
        v8);
    }
  }
  return (unsigned int)Guid;
}

```

## disassembly

```asm
0x18002f154  mov     [rsp+arg_8], rbx
0x18002f159  mov     [rsp+arg_10], rsi
0x18002f15e  push    rdi
0x18002f15f  sub     rsp, 0B0h
0x18002f166  mov     rax, cs:__security_cookie
0x18002f16d  xor     rax, rsp
0x18002f170  mov     [rsp+0B8h+var_18], rax
0x18002f178  lea     rdi, [rcx+40h]
0x18002f17c  cmp     qword ptr [rdi+10h], 0
0x18002f181  jz      short loc_18002F1ED
0x18002f183  mov     ebx, 80004005h
0x18002f188  mov     rax, cs:WPP_GLOBAL_Control
0x18002f18f  lea     rcx, WPP_GLOBAL_Control
0x18002f196  cmp     rax, rcx
0x18002f199  jz      loc_18002F259
0x18002f19f  test    byte ptr [rax+1Ch], 8
0x18002f1a3  jz      loc_18002F259
0x18002f1a9  cmp     byte ptr [rax+19h], 2
0x18002f1ad  jb      loc_18002F259
0x18002f1b3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002f1b8  mov     edx, 59h ; 'Y'
0x18002f1bd  mov     [rsp+0B8h+var_90], 80004005h
0x18002f1c5  lea     rcx, aAttemptingToOv; "Attempting to overwrite Workspace Id"
0x18002f1cc  mov     [rsp+0B8h+var_98], rcx
0x18002f1d1  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x18002f1d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f1df  mov     r9d, eax
0x18002f1e2  mov     rcx, [rcx+10h]
0x18002f1e6  call    WPP_SF_DsD
0x18002f1eb  jmp     short loc_18002F259
0x18002f1ed  lea     rsi, [rcx+30h]
0x18002f1f1  mov     rcx, rsi; pguid
0x18002f1f4  call    cs:__imp_CoCreateGuid
0x18002f1fa  mov     ebx, eax
0x18002f1fc  test    eax, eax
0x18002f1fe  jns     short loc_18002F236
0x18002f200  mov     rax, cs:WPP_GLOBAL_Control
0x18002f207  lea     rcx, WPP_GLOBAL_Control
0x18002f20e  cmp     rax, rcx
0x18002f211  jz      short loc_18002F259
0x18002f213  test    byte ptr [rax+1Ch], 8
0x18002f217  jz      short loc_18002F259
0x18002f219  cmp     byte ptr [rax+19h], 2
0x18002f21d  jb      short loc_18002F259
0x18002f21f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002f224  mov     edx, 5Ah ; 'Z'
0x18002f229  mov     [rsp+0B8h+var_90], ebx
0x18002f22d  lea     rcx, aCocreateguidFa; "CoCreateGuid failed"
0x18002f234  jmp     short loc_18002F1CC
0x18002f236  mov     r8d, 32h ; '2'; cchMax
0x18002f23c  lea     rdx, [rsp+0B8h+sz]; lpsz
0x18002f241  mov     rcx, rsi; rguid
0x18002f244  call    cs:__imp_StringFromGUID2
0x18002f24a  lea     rdx, [rsp+0B8h+sz]
0x18002f24f  mov     rcx, rdi
0x18002f252  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18002f257  xor     ebx, ebx
0x18002f259  mov     eax, ebx
0x18002f25b  mov     rcx, [rsp+0B8h+var_18]
0x18002f263  xor     rcx, rsp; StackCookie
0x18002f266  call    __security_check_cookie
0x18002f26b  lea     r11, [rsp+0B8h+var_8]
0x18002f273  mov     rbx, [r11+18h]
0x18002f277  mov     rsi, [r11+20h]
0x18002f27b  mov     rsp, r11
0x18002f27e  pop     rdi
0x18002f27f  retn
```
