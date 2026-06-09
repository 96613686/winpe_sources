# CBITSDownloadMonitor::CBITSDownloadMonitor(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,uchar,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x18001c79c`
- end: `0x18001c8db`
- name: `??0CBITSDownloadMonitor@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@E00@Z`
- size: `319`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180014680`

## callees

- `0x1800062ac`
- `0x18000702c`
- `0x18000a290`
- `0x18001c79c`
- `0x18001f420`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x18001c843`
- `KERNEL32!CreateEventW` at `0x18001c843`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CBITSDownloadMonitor::CBITSDownloadMonitor(__int64 a1, __int64 a2, char a3, __int64 a4, __int64 a5)
{
  HANDLE EventW; // rax
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rdx

  *(_QWORD *)a1 = &CBITSDownloadMonitor::`vftable'{for `IBackgroundCopyCallback'};
  *(_QWORD *)(a1 + 8) = &CBITSDownloadMonitor::`vftable'{for `IBITSDownloadMonitor'};
  std::wstring::wstring(a1 + 16, a5);
  *(_QWORD *)(a1 + 72) = 7;
  *(_QWORD *)(a1 + 64) = 0;
  *(_WORD *)(a1 + 48) = 0;
  *(_BYTE *)(a1 + 80) = a3;
  std::wstring::wstring(a1 + 88, a4);
  *(_WORD *)(a1 + 120) = 0;
  std::wstring::wstring(a1 + 128, a2);
  EventW = CreateEventW(0, 0, 0, 0);
  *(_QWORD *)(a1 + 176) = EventW;
  if ( (((unsigned __int64)EventW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0
    && WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[14] & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_c97e9bd2ae7c3d97c0f7a9732ba19b9f_Traceguids);
  }
  *(_DWORD *)(a1 + 124) = 1;
  LOBYTE(v10) = 1;
  std::wstring::_Tidy(a2, v10, 0);
  LOBYTE(v11) = 1;
  std::wstring::_Tidy(a4, v11, 0);
  LOBYTE(v12) = 1;
  std::wstring::_Tidy(a5, v12, 0);
  return a1;
}

```

## disassembly

```asm
0x18001c79c  mov     r11, rsp
0x18001c79f  push    rbx
0x18001c7a0  push    rbp
0x18001c7a1  push    rsi
0x18001c7a2  push    rdi
0x18001c7a3  push    r14
0x18001c7a5  sub     rsp, 50h
0x18001c7a9  mov     rax, cs:__security_cookie
0x18001c7b0  xor     rax, rsp
0x18001c7b3  mov     [rsp+78h+var_38], rax
0x18001c7b8  mov     rbp, r9
0x18001c7bb  mov     bl, r8b
0x18001c7be  mov     rsi, rdx
0x18001c7c1  mov     rdi, rcx
0x18001c7c4  mov     [r11-58h], rcx
0x18001c7c8  mov     [r11-50h], rdx
0x18001c7cc  mov     [r11-48h], r9
0x18001c7d0  mov     r14, [rsp+78h+arg_20]
0x18001c7d8  mov     [r11-40h], r14
0x18001c7dc  lea     rax, ??_7CBITSDownloadMonitor@@6BIBackgroundCopyCallback@@@; const CBITSDownloadMonitor::`vftable'{for `IBackgroundCopyCallback'}
0x18001c7e3  mov     [rcx], rax
0x18001c7e6  lea     rax, ??_7CBITSDownloadMonitor@@6BIBITSDownloadMonitor@@@; const CBITSDownloadMonitor::`vftable'{for `IBITSDownloadMonitor'}
0x18001c7ed  mov     [rcx+8], rax
0x18001c7f1  add     rcx, 10h
0x18001c7f5  mov     rdx, r14
0x18001c7f8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001c7fd  nop
0x18001c7fe  mov     qword ptr [rdi+48h], 7
0x18001c806  mov     qword ptr [rdi+40h], 0
0x18001c80e  xor     eax, eax
0x18001c810  mov     [rdi+30h], ax
0x18001c814  mov     [rdi+50h], bl
0x18001c817  lea     rcx, [rdi+58h]
0x18001c81b  mov     rdx, rbp
0x18001c81e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001c823  nop
0x18001c824  mov     word ptr [rdi+78h], 0
0x18001c82a  lea     rcx, [rdi+80h]
0x18001c831  mov     rdx, rsi
0x18001c834  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001c839  xor     r9d, r9d; lpName
0x18001c83c  xor     r8d, r8d; bInitialState
0x18001c83f  xor     edx, edx; bManualReset
0x18001c841  xor     ecx, ecx; lpEventAttributes
0x18001c843  call    cs:__imp_CreateEventW
0x18001c84a  nop     dword ptr [rax+rax+00h]
0x18001c84f  mov     [rdi+0B0h], rax
0x18001c856  inc     rax
0x18001c859  test    rax, 0FFFFFFFFFFFFFFFEh
0x18001c85f  jnz     short loc_18001C88F
0x18001c861  lea     rax, WPP_GLOBAL_Control
0x18001c868  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c86f  cmp     rcx, rax
0x18001c872  jz      short loc_18001C88F
0x18001c874  test    byte ptr [rcx+1Ch], 4
0x18001c878  jz      short loc_18001C88F
0x18001c87a  mov     edx, 0Ah
0x18001c87f  lea     r8, WPP_c97e9bd2ae7c3d97c0f7a9732ba19b9f_Traceguids
0x18001c886  mov     rcx, [rcx+10h]
0x18001c88a  call    WPP_SF_
0x18001c88f  mov     dword ptr [rdi+7Ch], 1
0x18001c896  xor     r8d, r8d
0x18001c899  mov     dl, 1
0x18001c89b  mov     rcx, rsi
0x18001c89e  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001c8a3  nop
0x18001c8a4  xor     r8d, r8d
0x18001c8a7  mov     dl, 1
0x18001c8a9  mov     rcx, rbp
0x18001c8ac  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001c8b1  nop
0x18001c8b2  xor     r8d, r8d
0x18001c8b5  mov     dl, 1
0x18001c8b7  mov     rcx, r14
0x18001c8ba  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001c8bf  mov     rax, rdi
0x18001c8c2  mov     rcx, [rsp+78h+var_38]
0x18001c8c7  xor     rcx, rsp; StackCookie
0x18001c8ca  call    __security_check_cookie
0x18001c8cf  add     rsp, 50h
0x18001c8d3  pop     r14
0x18001c8d5  pop     rdi
0x18001c8d6  pop     rsi
0x18001c8d7  pop     rbp
0x18001c8d8  pop     rbx
0x18001c8d9  retn
```
