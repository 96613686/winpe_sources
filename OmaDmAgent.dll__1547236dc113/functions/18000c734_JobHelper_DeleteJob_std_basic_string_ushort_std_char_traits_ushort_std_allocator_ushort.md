# JobHelper::DeleteJob(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x18000c734`
- end: `0x18000cb44`
- name: `?DeleteJob@JobHelper@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1040`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: ``

## callers

- `0x18000cb4c`
- `0x18000da10`

## callees

- `0x180002a50`
- `0x1800062ac`
- `0x18000702c`
- `0x1800076a0`
- `0x18000a2c0`
- `0x18000a358`
- `0x18000a3c0`
- `0x18000a4f4`
- `0x18000b6f4`
- `0x18000b7d8`
- `0x18000b8b4`
- `0x18000bae8`
- `0x18000bccc`
- `0x18000bd00`
- `0x18000c588`
- `0x18000c734`
- `0x18000ea88`
- `0x18000f924`
- `0x18000fdf8`
- `0x180012914`
- `0x180013ce4`
- `0x18001f420`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000c814`
- `KERNEL32!EnterCriticalSection` at `0x18000c814`
- `KERNEL32!LeaveCriticalSection` at `0x18000cae6`
- `KERNEL32!LeaveCriticalSection` at `0x18000cae6`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall JobHelper::DeleteJob(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rax
  int JobRegPath; // eax
  int v6; // ebx
  __int64 v7; // r9
  const unsigned __int16 *v8; // r12
  _QWORD *v9; // rax
  int Job; // eax
  __int64 v11; // r9
  _QWORD *v12; // r9
  __int64 v13; // rax
  int v14; // eax
  _QWORD *v15; // r9
  __int64 v16; // rbx
  _QWORD *v17; // rdx
  __int64 v18; // rax
  int v19; // eax
  _QWORD *v20; // rcx
  _QWORD *v21; // r9
  __int64 i; // rax
  _SwJob *v23; // rax
  __int64 v24; // rcx
  LSTATUS Key; // eax
  __int64 v26; // rdx
  __int64 v27; // rdx
  HKEY v29; // [rsp+38h] [rbp-C8h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v31[32]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD *v32; // [rsp+68h] [rbp-98h]
  unsigned __int16 *v33[4]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v34[29]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v35[9]; // [rsp+178h] [rbp+78h] BYREF
  __int64 *v36; // [rsp+1C0h] [rbp+C0h]
  _QWORD v37[11]; // [rsp+1D0h] [rbp+D0h] BYREF
  _QWORD v38[29]; // [rsp+228h] [rbp+128h] BYREF

  v32 = a2;
  std::wstring::wstring(v33, &dword_180022F6C);
  phkResult = 0;
  v29 = 0;
  v4 = std::wstring::wstring(v31, a2);
  JobRegPath = JobHelper::GetJobRegPath(v4, v33);
  v6 = JobRegPath;
  if ( JobRegPath >= 0 )
  {
    v8 = (const unsigned __int16 *)v33;
    if ( v33[3] >= (unsigned __int16 *)8 )
      v8 = v33[0];
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 128));
    _SwJob::_SwJob((_SwJob *)v34);
    v9 = (_QWORD *)std::wstring::wstring(v31, a2);
    Job = JobHelper::GetJob(a1, v9, (__int64)v34);
    v6 = Job;
    if ( Job >= 0 )
    {
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        if ( a2[3] < 8u )
          v12 = a2;
        else
          v12 = (_QWORD *)*a2;
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, &WPP_9f155fbe94773387205a22e9edb85311_Traceguids, v12);
      }
      if ( v35[2] )
      {
        v13 = std::wstring::wstring(v31, v35);
        v14 = CBitsDownloader::DeleteJob(a1, v13);
        if ( v14 < 0 && WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
        {
          v15 = v35;
          if ( v35[3] >= 8u )
            LODWORD(v15) = v35[0];
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            85,
            (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
            (_DWORD)v15,
            v14);
        }
      }
      v16 = *v36;
      while ( (__int64 *)v16 != v36 )
      {
        _FrameworkDependency::_FrameworkDependency(
          (_FrameworkDependency *)v37,
          (const struct _FrameworkDependency *)(v16 + 64));
        if ( v38[2] )
        {
          v17 = v38;
          if ( v38[3] >= 8u )
            v17 = (_QWORD *)v38[0];
          v18 = std::wstring::wstring(v31, v17);
          v19 = CBitsDownloader::DeleteJob(a1, v18);
          if ( v19 < 0 && WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
          {
            v20 = v37;
            if ( v37[3] >= 8u )
              v20 = (_QWORD *)v37[0];
            v21 = v34;
            if ( v34[3] >= 8u )
              LODWORD(v21) = v34[0];
            WPP_SF_SSD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              86,
              (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
              (_DWORD)v21,
              (__int64)v20,
              v19);
          }
        }
        _FrameworkDependency::~_FrameworkDependency((_FrameworkDependency *)v37);
        if ( !*(_BYTE *)(v16 + 25) )
        {
          if ( *(_BYTE *)(*(_QWORD *)(v16 + 16) + 25LL) )
          {
            for ( i = *(_QWORD *)(v16 + 8); !*(_BYTE *)(i + 25) && v16 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
              v16 = i;
          }
          else
          {
            i = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,_FrameworkDependency>>>::_Min();
          }
          v16 = i;
        }
      }
      v23 = _SwJob::_SwJob((_SwJob *)v37, (const struct _SwJob *)v34);
      JobHelper::DeleteContent(v24, (__int64)v23);
      Key = CurrentUserRegKeyHelper::GetKey(&phkResult, &v29);
      v6 = Key;
      if ( Key >= 0 )
      {
        v6 = DeleteRegKeyRecursive(v29, v8);
        if ( v6 < 0 && WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, &WPP_9f155fbe94773387205a22e9edb85311_Traceguids, v8);
      }
      else if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          87,
          &WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
          (unsigned int)Key);
      }
    }
    else if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    {
      if ( a2[3] < 8u )
        LODWORD(v11) = (_DWORD)a2;
      else
        v11 = *a2;
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        83,
        (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
        v11,
        Job);
    }
    _SwJob::~_SwJob((_SwJob *)v34);
  }
  else if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
  {
    if ( a2[3] < 8u )
      LODWORD(v7) = (_DWORD)a2;
    else
      v7 = *a2;
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      82,
      (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
      v7,
      JobRegPath);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 128));
  CurrentUserRegKeyHelper::~CurrentUserRegKeyHelper((CurrentUserRegKeyHelper *)&phkResult);
  LOBYTE(v26) = 1;
  std::wstring::_Tidy(v33, v26, 0);
  LOBYTE(v27) = 1;
  std::wstring::_Tidy(a2, v27, 0);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000c734  mov     [rsp-8+arg_10], rbx
0x18000c739  push    rbp
0x18000c73a  push    rsi
0x18000c73b  push    rdi
0x18000c73c  push    r12
0x18000c73e  push    r14
0x18000c740  lea     rbp, [rsp-220h]
0x18000c748  sub     rsp, 320h
0x18000c74f  mov     rax, cs:__security_cookie
0x18000c756  xor     rax, rsp
0x18000c759  mov     [rbp+240h+var_30], rax
0x18000c760  mov     rdi, rdx
0x18000c763  mov     r14, rcx
0x18000c766  mov     [rsp+340h+var_2D8], rdx
0x18000c76b  lea     rdx, dword_180022F6C
0x18000c772  lea     rcx, [rsp+340h+var_2D0]
0x18000c777  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000c77c  nop
0x18000c77d  mov     [rsp+340h+phkResult], 0
0x18000c786  mov     [rsp+340h+var_308], 0
0x18000c78f  mov     rdx, rdi
0x18000c792  lea     rcx, [rsp+340h+var_2F8]
0x18000c797  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000c79c  lea     rdx, [rsp+340h+var_2D0]
0x18000c7a1  mov     rcx, rax
0x18000c7a4  call    ?GetJobRegPath@JobHelper@@CAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; JobHelper::GetJobRegPath(std::wstring,std::wstring &)
0x18000c7a9  mov     ebx, eax
0x18000c7ab  test    eax, eax
0x18000c7ad  jns     short loc_18000C7FD
0x18000c7af  lea     rsi, WPP_GLOBAL_Control
0x18000c7b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c7bd  cmp     rcx, rsi
0x18000c7c0  jz      loc_18000CADF
0x18000c7c6  test    byte ptr [rcx+1Ch], 4
0x18000c7ca  jz      loc_18000CADF
0x18000c7d0  cmp     qword ptr [rdi+18h], 8
0x18000c7d5  jb      short loc_18000C7DC
0x18000c7d7  mov     r9, [rdi]
0x18000c7da  jmp     short loc_18000C7DF
0x18000c7dc  mov     r9, rdi
0x18000c7df  mov     edx, 52h ; 'R'
0x18000c7e4  mov     dword ptr [rsp+340h+var_320], eax
0x18000c7e8  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x18000c7ef  mov     rcx, [rcx+10h]
0x18000c7f3  call    WPP_SF_Sd
0x18000c7f8  jmp     loc_18000CADF
0x18000c7fd  lea     r12, [rsp+340h+var_2D0]
0x18000c802  cmp     [rbp+240h+var_2B8], 8
0x18000c807  cmovnb  r12, [rsp+340h+var_2D0]
0x18000c80d  lea     rcx, [r14+80h]; lpCriticalSection
0x18000c814  call    cs:__imp_EnterCriticalSection
0x18000c81b  nop     dword ptr [rax+rax+00h]
0x18000c820  lea     rcx, [rbp+240h+var_2B0]; this
0x18000c824  call    ??0_SwJob@@QEAA@XZ; _SwJob::_SwJob(void)
0x18000c829  nop
0x18000c82a  mov     rdx, rdi
0x18000c82d  lea     rcx, [rsp+340h+var_2F8]
0x18000c832  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000c837  lea     r8, [rbp+240h+var_2B0]
0x18000c83b  mov     rdx, rax
0x18000c83e  mov     rcx, r14
0x18000c841  call    ?GetJob@JobHelper@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAU_SwJob@@@Z; JobHelper::GetJob(std::wstring,_SwJob &)
0x18000c846  mov     ebx, eax
0x18000c848  test    eax, eax
0x18000c84a  jns     short loc_18000C89A
0x18000c84c  lea     rsi, WPP_GLOBAL_Control
0x18000c853  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c85a  cmp     rcx, rsi
0x18000c85d  jz      loc_18000CAD6
0x18000c863  test    byte ptr [rcx+1Ch], 4
0x18000c867  jz      loc_18000CAD6
0x18000c86d  cmp     qword ptr [rdi+18h], 8
0x18000c872  jb      short loc_18000C879
0x18000c874  mov     r9, [rdi]
0x18000c877  jmp     short loc_18000C87C
0x18000c879  mov     r9, rdi
0x18000c87c  mov     edx, 53h ; 'S'
0x18000c881  mov     dword ptr [rsp+340h+var_320], eax
0x18000c885  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x18000c88c  mov     rcx, [rcx+10h]
0x18000c890  call    WPP_SF_Sd
0x18000c895  jmp     loc_18000CAD6
0x18000c89a  lea     rsi, WPP_GLOBAL_Control
0x18000c8a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c8a8  cmp     rcx, rsi
0x18000c8ab  jz      short loc_18000C8D7
0x18000c8ad  test    byte ptr [rcx+1Ch], 1
0x18000c8b1  jz      short loc_18000C8D7
0x18000c8b3  cmp     qword ptr [rdi+18h], 8
0x18000c8b8  jb      short loc_18000C8BF
0x18000c8ba  mov     r9, [rdi]
0x18000c8bd  jmp     short loc_18000C8C2
0x18000c8bf  mov     r9, rdi
0x18000c8c2  mov     edx, 54h ; 'T'
0x18000c8c7  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x18000c8ce  mov     rcx, [rcx+10h]
0x18000c8d2  call    WPP_SF_S
0x18000c8d7  cmp     [rbp+240h+var_1B8], 0
0x18000c8df  jz      short loc_18000C93A
0x18000c8e1  lea     rdx, [rbp+240h+var_1C8]
0x18000c8e5  lea     rcx, [rsp+340h+var_2F8]
0x18000c8ea  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000c8ef  mov     rdx, rax
0x18000c8f2  mov     rcx, r14
0x18000c8f5  call    ?DeleteJob@CBitsDownloader@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CBitsDownloader::DeleteJob(std::wstring)
0x18000c8fa  test    eax, eax
0x18000c8fc  jns     short loc_18000C93A
0x18000c8fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c905  cmp     rcx, rsi
0x18000c908  jz      short loc_18000C93A
0x18000c90a  test    byte ptr [rcx+1Ch], 2
0x18000c90e  jz      short loc_18000C93A
0x18000c910  lea     r9, [rbp+240h+var_1C8]
0x18000c914  cmp     [rbp+240h+var_1B0], 8
0x18000c91c  cmovnb  r9, [rbp+240h+var_1C8]
0x18000c921  mov     edx, 55h ; 'U'
0x18000c926  mov     dword ptr [rsp+340h+var_320], eax
0x18000c92a  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x18000c931  mov     rcx, [rcx+10h]
0x18000c935  call    WPP_SF_Sd
0x18000c93a  mov     rbx, [rbp+240h+var_180]
0x18000c941  mov     rbx, [rbx]
0x18000c944  cmp     rbx, [rbp+240h+var_180]
0x18000c94b  jz      loc_18000CA3F
0x18000c951  lea     rdx, [rbx+40h]; struct _FrameworkDependency *
0x18000c955  lea     rcx, [rbp+240h+var_170]; this
0x18000c95c  call    ??0_FrameworkDependency@@QEAA@AEBU0@@Z; _FrameworkDependency::_FrameworkDependency(_FrameworkDependency const &)
0x18000c961  nop
0x18000c962  cmp     [rbp+240h+var_108], 0
0x18000c96a  jz      loc_18000C9F7
0x18000c970  lea     rdx, [rbp+240h+var_118]
0x18000c977  cmp     [rbp+240h+var_100], 8
0x18000c97f  cmovnb  rdx, [rbp+240h+var_118]
0x18000c987  lea     rcx, [rsp+340h+var_2F8]
0x18000c98c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000c991  mov     rdx, rax
0x18000c994  mov     rcx, r14
0x18000c997  call    ?DeleteJob@CBitsDownloader@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CBitsDownloader::DeleteJob(std::wstring)
0x18000c99c  test    eax, eax
0x18000c99e  jns     short loc_18000C9F7
0x18000c9a0  mov     r10, cs:WPP_GLOBAL_Control
0x18000c9a7  cmp     r10, rsi
0x18000c9aa  jz      short loc_18000C9F7
0x18000c9ac  test    byte ptr [r10+1Ch], 2
0x18000c9b1  jz      short loc_18000C9F7
0x18000c9b3  lea     rcx, [rbp+240h+var_170]
0x18000c9ba  cmp     [rbp+240h+var_158], 8
0x18000c9c2  cmovnb  rcx, [rbp+240h+var_170]
0x18000c9ca  lea     r9, [rbp+240h+var_2B0]
0x18000c9ce  cmp     [rbp+240h+var_298], 8
0x18000c9d3  cmovnb  r9, [rbp+240h+var_2B0]
0x18000c9d8  mov     edx, 56h ; 'V'
0x18000c9dd  mov     [rsp+340h+var_318], eax
0x18000c9e1  mov     [rsp+340h+var_320], rcx
0x18000c9e6  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x18000c9ed  mov     rcx, [r10+10h]
0x18000c9f1  call    WPP_SF_SSD
0x18000c9f6  nop
0x18000c9f7  lea     rcx, [rbp+240h+var_170]; this
0x18000c9fe  call    ??1_FrameworkDependency@@QEAA@XZ; _FrameworkDependency::~_FrameworkDependency(void)
0x18000ca03  cmp     byte ptr [rbx+19h], 0
0x18000ca07  jnz     loc_18000C944
0x18000ca0d  mov     rcx, [rbx+10h]
0x18000ca11  cmp     byte ptr [rcx+19h], 0
0x18000ca15  jnz     short loc_18000CA1E
0x18000ca17  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FrameworkDependency@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FrameworkDependency@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,_FrameworkDependency>>>::_Min(std::_Tree_node<std::pair<std::wstring const,_FrameworkDependency>,void *> *)
0x18000ca1c  jmp     short loc_18000CA37
0x18000ca1e  mov     rax, [rbx+8]
0x18000ca22  jmp     short loc_18000CA31
0x18000ca24  cmp     rbx, [rax+10h]
0x18000ca28  jnz     short loc_18000CA37
0x18000ca2a  mov     rbx, rax
0x18000ca2d  mov     rax, [rax+8]
0x18000ca31  cmp     byte ptr [rax+19h], 0
0x18000ca35  jz      short loc_18000CA24
0x18000ca37  mov     rbx, rax
0x18000ca3a  jmp     loc_18000C944
0x18000ca3f  lea     rdx, [rbp+240h+var_2B0]; struct _SwJob *
0x18000ca43  lea     rcx, [rbp+240h+var_170]; this
0x18000ca4a  call    ??0_SwJob@@QEAA@AEBU0@@Z; _SwJob::_SwJob(_SwJob const &)
0x18000ca4f  mov     rdx, rax
0x18000ca52  call    ?DeleteContent@JobHelper@@AEAAJU_SwJob@@@Z; JobHelper::DeleteContent(_SwJob)
0x18000ca57  lea     rdx, [rsp+340h+var_308]; HKEY *
0x18000ca5c  lea     rcx, [rsp+340h+phkResult]; phkResult
0x18000ca61  call    ?GetKey@CurrentUserRegKeyHelper@@QEAAJAEAPEAUHKEY__@@@Z; CurrentUserRegKeyHelper::GetKey(HKEY__ * &)
0x18000ca66  mov     ebx, eax
0x18000ca68  test    eax, eax
0x18000ca6a  jns     short loc_18000CA98
0x18000ca6c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ca73  cmp     rcx, rsi
0x18000ca76  jz      short loc_18000CAD6
0x18000ca78  test    byte ptr [rcx+1Ch], 4
0x18000ca7c  jz      short loc_18000CAD6
0x18000ca7e  mov     edx, 57h ; 'W'
0x18000ca83  mov     r9d, eax
0x18000ca86  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x18000ca8d  mov     rcx, [rcx+10h]
0x18000ca91  call    WPP_SF_d
0x18000ca96  jmp     short loc_18000CAD6
0x18000ca98  mov     rdx, r12; unsigned __int16 *
0x18000ca9b  mov     rcx, [rsp+340h+var_308]; HKEY
0x18000caa0  call    ?DeleteRegKeyRecursive@@YAJPEAUHKEY__@@PEBG@Z; DeleteRegKeyRecursive(HKEY__ *,ushort const *)
0x18000caa5  mov     ebx, eax
0x18000caa7  test    eax, eax
0x18000caa9  jns     short loc_18000CAD6
0x18000caab  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cab2  cmp     rcx, rsi
0x18000cab5  jz      short loc_18000CAD6
0x18000cab7  test    byte ptr [rcx+1Ch], 4
0x18000cabb  jz      short loc_18000CAD6
0x18000cabd  mov     edx, 58h ; 'X'
0x18000cac2  mov     r9, r12
0x18000cac5  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x18000cacc  mov     rcx, [rcx+10h]
0x18000cad0  call    WPP_SF_S
0x18000cad5  nop
0x18000cad6  lea     rcx, [rbp+240h+var_2B0]; this
0x18000cada  call    ??1_SwJob@@QEAA@XZ; _SwJob::~_SwJob(void)
0x18000cadf  lea     rcx, [r14+80h]; lpCriticalSection
0x18000cae6  call    cs:__imp_LeaveCriticalSection
0x18000caed  nop     dword ptr [rax+rax+00h]
0x18000caf2  nop
0x18000caf3  lea     rcx, [rsp+340h+phkResult]; this
0x18000caf8  call    ??1CurrentUserRegKeyHelper@@QEAA@XZ; CurrentUserRegKeyHelper::~CurrentUserRegKeyHelper(void)
0x18000cafd  nop
0x18000cafe  xor     r8d, r8d
0x18000cb01  mov     dl, 1
0x18000cb03  lea     rcx, [rsp+340h+var_2D0]
0x18000cb08  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000cb0d  nop
0x18000cb0e  xor     r8d, r8d
0x18000cb11  mov     dl, 1
0x18000cb13  mov     rcx, rdi
0x18000cb16  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000cb1b  mov     eax, ebx
0x18000cb1d  mov     rcx, [rbp+240h+var_30]
0x18000cb24  xor     rcx, rsp; StackCookie
0x18000cb27  call    __security_check_cookie
0x18000cb2c  mov     rbx, [rsp+340h+arg_10]
0x18000cb34  add     rsp, 320h
0x18000cb3b  pop     r14
0x18000cb3d  pop     r12
0x18000cb3f  pop     rdi
0x18000cb40  pop     rsi
0x18000cb41  pop     rbp
0x18000cb42  retn
```
