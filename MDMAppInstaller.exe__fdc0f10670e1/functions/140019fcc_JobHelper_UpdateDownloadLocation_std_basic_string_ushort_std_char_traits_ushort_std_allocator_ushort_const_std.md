# JobHelper::UpdateDownloadLocation(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x140019fcc`
- end: `0x14001a0bb`
- name: `?UpdateDownloadLocation@JobHelper@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@0@Z`
- size: `239`
- prototype: `__int64 __fastcall(_QWORD *, __int64, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000d470`
- `0x14000d898`
- `0x140018e48`

## callees

- `0x1400036ac`
- `0x140006480`
- `0x14000740c`
- `0x140018520`
- `0x140019750`
- `0x140019fcc`
- `0x14001a8d0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x14001a06e`
- `KERNEL32!LeaveCriticalSection` at `0x14001a06e`
- `KERNEL32!EnterCriticalSection` at `0x14001a005`
- `KERNEL32!EnterCriticalSection` at `0x14001a005`

## string_xrefs

- `0x14001a088`: `UpdateDownloadLocation for Job %1 to failed. Error = 0x%2!x!.`

## pseudocode

```c
__int64 __fastcall JobHelper::UpdateDownloadLocation(_QWORD *a1, __int64 a2, const unsigned __int16 *a3)
{
  HKEY v6; // rcx
  int JobRegPath; // ebx
  const unsigned __int16 *v8; // rdx
  int v9; // eax
  __int64 v10; // rdx
  struct _SECURITY_ATTRIBUTES *v12; // [rsp+20h] [rbp-58h]
  int v13; // [rsp+28h] [rbp-50h]
  unsigned __int16 *v14[4]; // [rsp+30h] [rbp-48h] BYREF

  std::wstring::wstring(v14, &word_14001E5B4);
  EnterCriticalSection(&JobHelper::m_critSec);
  JobRegPath = JobHelper::GetJobRegPath(a1, a2, v14);
  if ( JobRegPath >= 0 )
  {
    if ( *((_QWORD *)a3 + 3) >= 8u )
      a3 = *(const unsigned __int16 **)a3;
    v8 = (const unsigned __int16 *)v14;
    if ( v14[3] >= (unsigned __int16 *)8 )
      v8 = v14[0];
    v9 = WriteRegSZValue(v6, v8, (const unsigned __int16 *)&stru_140026260, a3, v12, v13);
    JobRegPath = v9;
    if ( v9 < 0 )
      LogError(L"failed to set %1 ,0x%2!x!", &stru_140026260, (unsigned int)v9);
  }
  LeaveCriticalSection(&JobHelper::m_critSec);
  if ( JobRegPath < 0 )
  {
    if ( a1[3] >= 8u )
      a1 = (_QWORD *)*a1;
    LogError(L"UpdateDownloadLocation for Job %1 to failed. Error = 0x%2!x!.", a1, (unsigned int)JobRegPath);
  }
  LOBYTE(v10) = 1;
  std::wstring::_Tidy(v14, v10, 0);
  return (unsigned int)JobRegPath;
}

```

## disassembly

```asm
0x140019fcc  push    rbx
0x140019fce  push    rsi
0x140019fcf  push    rdi
0x140019fd0  sub     rsp, 60h
0x140019fd4  mov     rax, cs:__security_cookie
0x140019fdb  xor     rax, rsp
0x140019fde  mov     [rsp+78h+var_28], rax
0x140019fe3  mov     rsi, r8
0x140019fe6  mov     rbx, rdx
0x140019fe9  mov     rdi, rcx
0x140019fec  lea     rdx, word_14001E5B4
0x140019ff3  lea     rcx, [rsp+78h+var_48]
0x140019ff8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x140019ffd  nop
0x140019ffe  lea     rcx, ?m_critSec@JobHelper@@0VCComAutoCriticalSection@ATL@@A; lpCriticalSection
0x14001a005  call    cs:__imp_EnterCriticalSection
0x14001a00b  lea     r8, [rsp+78h+var_48]
0x14001a010  mov     rdx, rbx
0x14001a013  mov     rcx, rdi
0x14001a016  call    ?GetJobRegPath@JobHelper@@CAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV23@@Z; JobHelper::GetJobRegPath(std::wstring const &,std::wstring const &,std::wstring &)
0x14001a01b  mov     ebx, eax
0x14001a01d  test    eax, eax
0x14001a01f  js      short loc_14001A067
0x14001a021  cmp     qword ptr [rsi+18h], 8
0x14001a026  jb      short loc_14001A02B
0x14001a028  mov     rsi, [rsi]
0x14001a02b  lea     rdx, [rsp+78h+var_48]
0x14001a030  cmp     [rsp+78h+var_30], 8
0x14001a036  cmovnb  rdx, [rsp+78h+var_48]; unsigned __int16 *
0x14001a03c  mov     r9, rsi; unsigned __int16 *
0x14001a03f  lea     r8, stru_140026260; unsigned __int16 *
0x14001a046  call    ?WriteRegSZValue@@YAJPEAUHKEY__@@PEBG11PEAU_SECURITY_ATTRIBUTES@@H@Z; WriteRegSZValue(HKEY__ *,ushort const *,ushort const *,ushort const *,_SECURITY_ATTRIBUTES *,int)
0x14001a04b  mov     ebx, eax
0x14001a04d  test    eax, eax
0x14001a04f  jns     short loc_14001A067
0x14001a051  mov     r8d, eax
0x14001a054  lea     rdx, stru_140026260
0x14001a05b  lea     rcx, aFailedToSet10x; "failed to set %1 ,0x%2!x!"
0x14001a062  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x14001a067  lea     rcx, ?m_critSec@JobHelper@@0VCComAutoCriticalSection@ATL@@A; lpCriticalSection
0x14001a06e  call    cs:__imp_LeaveCriticalSection
0x14001a074  test    ebx, ebx
0x14001a076  jns     short loc_14001A095
0x14001a078  cmp     qword ptr [rdi+18h], 8
0x14001a07d  jb      short loc_14001A082
0x14001a07f  mov     rdi, [rdi]
0x14001a082  mov     r8d, ebx
0x14001a085  mov     rdx, rdi
0x14001a088  lea     rcx, aUpdatedownload; "UpdateDownloadLocation for Job %1 to fa"...
0x14001a08f  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x14001a094  nop
0x14001a095  xor     r8d, r8d
0x14001a098  mov     dl, 1
0x14001a09a  lea     rcx, [rsp+78h+var_48]
0x14001a09f  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14001a0a4  mov     eax, ebx
0x14001a0a6  mov     rcx, [rsp+78h+var_28]
0x14001a0ab  xor     rcx, rsp; StackCookie
0x14001a0ae  call    __security_check_cookie
0x14001a0b3  add     rsp, 60h
0x14001a0b7  pop     rdi
0x14001a0b8  pop     rsi
0x14001a0b9  pop     rbx
0x14001a0ba  retn
```
