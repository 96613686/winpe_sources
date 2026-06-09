# JobHelper::UpdateCurrentDownloadUrl(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x140019d68`
- end: `0x140019e8b`
- name: `?UpdateCurrentDownloadUrl@JobHelper@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@K0@Z`
- size: `291`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140019ba8`

## callees

- `0x1400036ac`
- `0x140006480`
- `0x14000740c`
- `0x1400182dc`
- `0x140018520`
- `0x140019750`
- `0x140019d68`
- `0x14001a8d0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x140019e3d`
- `KERNEL32!LeaveCriticalSection` at `0x140019e3d`
- `KERNEL32!EnterCriticalSection` at `0x140019da5`
- `KERNEL32!EnterCriticalSection` at `0x140019da5`

## string_xrefs

- `0x140019e57`: `UpdateCurrentDownloadUrl for Job %1. Error = 0x%2!x!.`

## pseudocode

```c
__int64 __fastcall JobHelper::UpdateCurrentDownloadUrl(
        _QWORD *a1,
        _QWORD *a2,
        unsigned int a3,
        const unsigned __int16 *a4)
{
  HKEY v8; // rcx
  int JobRegPath; // ebx
  const unsigned __int16 *v10; // rdx
  int v11; // eax
  HKEY v12; // rcx
  const unsigned __int16 *v13; // rdx
  const unsigned __int16 *v14; // rdx
  struct _SECURITY_ATTRIBUTES *v16; // [rsp+20h] [rbp-68h]
  struct _SECURITY_ATTRIBUTES *v17; // [rsp+20h] [rbp-68h]
  int v18; // [rsp+28h] [rbp-60h]
  unsigned __int16 *v19[3]; // [rsp+30h] [rbp-58h] BYREF
  unsigned __int64 v20; // [rsp+48h] [rbp-40h]

  std::wstring::wstring((__int64)v19, (__int64)&word_14001E5B4);
  EnterCriticalSection(&JobHelper::m_critSec);
  JobRegPath = JobHelper::GetJobRegPath(a1, a2, v19);
  if ( JobRegPath >= 0 )
  {
    v10 = (const unsigned __int16 *)v19;
    if ( v20 >= 8 )
      v10 = v19[0];
    v11 = WriteRegDWORDValue(v8, v10, L"CurrentDownloadUrlIndex", a3, v16);
    JobRegPath = v11;
    if ( v11 < 0 )
    {
      v13 = L"CurrentDownloadUrlIndex";
LABEL_12:
      LogError(L"failed to set %1 ,0x%2!x!", v13, (unsigned int)v11);
      goto LABEL_13;
    }
    if ( *((_QWORD *)a4 + 3) >= 8u )
      a4 = *(const unsigned __int16 **)a4;
    v14 = (const unsigned __int16 *)v19;
    if ( v20 >= 8 )
      v14 = v19[0];
    v11 = WriteRegSZValue(v12, v14, L"CurrentDownloadUrl", a4, v17, v18);
    JobRegPath = v11;
    if ( v11 < 0 )
    {
      v13 = L"CurrentDownloadUrl";
      goto LABEL_12;
    }
  }
LABEL_13:
  LeaveCriticalSection(&JobHelper::m_critSec);
  if ( JobRegPath < 0 )
  {
    if ( a1[3] >= 8u )
      a1 = (_QWORD *)*a1;
    LogError(L"UpdateCurrentDownloadUrl for Job %1. Error = 0x%2!x!.", a1, (unsigned int)JobRegPath);
  }
  std::wstring::_Tidy(v19, 1, 0);
  return (unsigned int)JobRegPath;
}

```

## disassembly

```asm
0x140019d68  push    rbx
0x140019d6a  push    rbp
0x140019d6b  push    rsi
0x140019d6c  push    rdi
0x140019d6d  sub     rsp, 68h
0x140019d71  mov     rax, cs:__security_cookie
0x140019d78  xor     rax, rsp
0x140019d7b  mov     [rsp+88h+var_38], rax
0x140019d80  mov     rsi, r9
0x140019d83  mov     ebp, r8d
0x140019d86  mov     rbx, rdx
0x140019d89  mov     rdi, rcx
0x140019d8c  lea     rdx, word_14001E5B4
0x140019d93  lea     rcx, [rsp+88h+var_58]
0x140019d98  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x140019d9d  nop
0x140019d9e  lea     rcx, ?m_critSec@JobHelper@@0VCComAutoCriticalSection@ATL@@A; lpCriticalSection
0x140019da5  call    cs:__imp_EnterCriticalSection
0x140019dab  lea     r8, [rsp+88h+var_58]
0x140019db0  mov     rdx, rbx
0x140019db3  mov     rcx, rdi
0x140019db6  call    ?GetJobRegPath@JobHelper@@CAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV23@@Z; JobHelper::GetJobRegPath(std::wstring const &,std::wstring const &,std::wstring &)
0x140019dbb  mov     ebx, eax
0x140019dbd  test    eax, eax
0x140019dbf  js      short loc_140019E36
0x140019dc1  lea     rdx, [rsp+88h+var_58]
0x140019dc6  cmp     [rsp+88h+var_40], 8
0x140019dcc  cmovnb  rdx, [rsp+88h+var_58]; unsigned __int16 *
0x140019dd2  mov     r9d, ebp; unsigned int
0x140019dd5  lea     r8, aCurrentdownloa; "CurrentDownloadUrlIndex"
0x140019ddc  call    ?WriteRegDWORDValue@@YAJPEAUHKEY__@@PEBG1KPEAU_SECURITY_ATTRIBUTES@@@Z; WriteRegDWORDValue(HKEY__ *,ushort const *,ushort const *,ulong,_SECURITY_ATTRIBUTES *)
0x140019de1  mov     ebx, eax
0x140019de3  test    eax, eax
0x140019de5  jns     short loc_140019DF0
0x140019de7  lea     rdx, aCurrentdownloa; "CurrentDownloadUrlIndex"
0x140019dee  jmp     short loc_140019E27
0x140019df0  cmp     qword ptr [rsi+18h], 8
0x140019df5  jb      short loc_140019DFA
0x140019df7  mov     rsi, [rsi]
0x140019dfa  lea     rdx, [rsp+88h+var_58]
0x140019dff  cmp     [rsp+88h+var_40], 8
0x140019e05  cmovnb  rdx, [rsp+88h+var_58]; unsigned __int16 *
0x140019e0b  mov     r9, rsi; unsigned __int16 *
0x140019e0e  lea     r8, aCurrentdownloa_0; "CurrentDownloadUrl"
0x140019e15  call    ?WriteRegSZValue@@YAJPEAUHKEY__@@PEBG11PEAU_SECURITY_ATTRIBUTES@@H@Z; WriteRegSZValue(HKEY__ *,ushort const *,ushort const *,ushort const *,_SECURITY_ATTRIBUTES *,int)
0x140019e1a  mov     ebx, eax
0x140019e1c  test    eax, eax
0x140019e1e  jns     short loc_140019E36
0x140019e20  lea     rdx, aCurrentdownloa_0; "CurrentDownloadUrl"
0x140019e27  mov     r8d, eax
0x140019e2a  lea     rcx, aFailedToSet10x; "failed to set %1 ,0x%2!x!"
0x140019e31  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140019e36  lea     rcx, ?m_critSec@JobHelper@@0VCComAutoCriticalSection@ATL@@A; lpCriticalSection
0x140019e3d  call    cs:__imp_LeaveCriticalSection
0x140019e43  test    ebx, ebx
0x140019e45  jns     short loc_140019E64
0x140019e47  cmp     qword ptr [rdi+18h], 8
0x140019e4c  jb      short loc_140019E51
0x140019e4e  mov     rdi, [rdi]
0x140019e51  mov     r8d, ebx
0x140019e54  mov     rdx, rdi
0x140019e57  lea     rcx, aUpdatecurrentd; "UpdateCurrentDownloadUrl for Job %1. Er"...
0x140019e5e  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140019e63  nop
0x140019e64  xor     r8d, r8d
0x140019e67  mov     dl, 1
0x140019e69  lea     rcx, [rsp+88h+var_58]
0x140019e6e  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140019e73  mov     eax, ebx
0x140019e75  mov     rcx, [rsp+88h+var_38]
0x140019e7a  xor     rcx, rsp; StackCookie
0x140019e7d  call    __security_check_cookie
0x140019e82  add     rsp, 68h
0x140019e86  pop     rdi
0x140019e87  pop     rsi
0x140019e88  pop     rbp
0x140019e89  pop     rbx
0x140019e8a  retn
```
