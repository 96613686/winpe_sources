# CApplicationManager::UpdateVolumeForAllAppsInSession(ulong,AudioVolumeChangeType)

- ea: `0x180015fe0`
- end: `0x1800161c3`
- name: `?UpdateVolumeForAllAppsInSession@CApplicationManager@@QEAAJKW4AudioVolumeChangeType@@@Z`
- size: `483`
- prototype: ``
- caller_count: `9`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x180015dd0`
- `0x180020d80`
- `0x180022390`
- `0x180024bf0`
- `0x1800274fc`
- `0x18002d704`
- `0x18002d840`
- `0x180039230`
- `0x18003c6c0`

## callees

- `0x180015fe0`
- `0x180017470`
- `0x180017590`
- `0x180017cb8`
- `0x180031960`
- `0x18003a5fc`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001601c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016053`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016065`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016110`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001601c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016053`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016065`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016110`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800160b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800160d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001618c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001619a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800160b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800160d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001618c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001619a`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CApplicationManager::UpdateVolumeForAllAppsInSession(__int64 a1, int a2, int a3)
{
  int v3; // r13d
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  _QWORD *v6; // rax
  _QWORD *v7; // r14
  __int64 v8; // rsi
  struct _RTL_CRITICAL_SECTION *v9; // r15
  _QWORD *v10; // rdi
  int v11; // r15d
  __int64 v12; // rbp
  int v14; // eax
  _QWORD *v15; // rdx
  AudioStateMonitorManager *v16; // rcx
  int v17; // [rsp+20h] [rbp-D8h]
  int v18; // [rsp+28h] [rbp-D0h] BYREF
  int v19; // [rsp+30h] [rbp-C8h]
  struct _RTL_CRITICAL_SECTION *v20; // [rsp+38h] [rbp-C0h]
  struct _RTL_CRITICAL_SECTION *v21; // [rsp+40h] [rbp-B8h]
  __int64 v22; // [rsp+48h] [rbp-B0h]
  __int64 v23; // [rsp+50h] [rbp-A8h]
  _QWORD v24[7]; // [rsp+60h] [rbp-98h] BYREF
  _QWORD *v25; // [rsp+98h] [rbp-60h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v17 = a3;
  v3 = a2;
  v19 = a2;
  v5 = (struct _RTL_CRITICAL_SECTION *)(a1 + 32);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 32));
  v20 = v5;
  v6 = *(_QWORD **)(a1 + 72);
  if ( v6 )
  {
    do
    {
      v7 = (_QWORD *)*v6;
      v8 = v6[2];
      if ( *(_DWORD *)(v8 + 212) == v3 )
      {
        EnterCriticalSection(v5);
        v21 = v5;
        v9 = (struct _RTL_CRITICAL_SECTION *)(v8 + 32);
        EnterCriticalSection((LPCRITICAL_SECTION)(v8 + 32));
        v22 = v8 + 32;
        v10 = *(_QWORD **)(v8 + 72);
        if ( v10 )
        {
          v11 = v17;
          do
          {
            v12 = v10[2];
            v10 = (_QWORD *)*v10;
            if ( !*(_DWORD *)(v12 + 416) )
            {
              v18 = v11;
              EnterCriticalSection((LPCRITICAL_SECTION)(v12 + 24));
              v23 = v12 + 24;
              v24[0] = off_18004FC98;
              v24[1] = &v18;
              v25 = v24;
              v14 = CProcess::ForEachSession<IAudioSessionPolicyControl>(v12, v24);
              if ( v14 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0xDA6,
                  (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\application.cpp",
                  (const char *)(unsigned int)v14,
                  v17);
              if ( v25 )
              {
                v15 = v24;
                LOBYTE(v15) = v25 != v24;
                (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v25 + 32LL))(v25, v15);
              }
              v16 = *(AudioStateMonitorManager **)(v12 + 704);
              if ( v16 )
                AudioStateMonitorManager::RecalculateVolume(v16);
              if ( v12 != -24 )
                LeaveCriticalSection((LPCRITICAL_SECTION)(v12 + 24));
            }
          }
          while ( v10 );
          v9 = (struct _RTL_CRITICAL_SECTION *)(v8 + 32);
          v3 = v19;
        }
        CApplication::NotifyVolumePolicyChange((CApplication *)v8);
        if ( v9 )
          LeaveCriticalSection(v9);
        if ( v5 )
          LeaveCriticalSection(v5);
      }
      v6 = v7;
    }
    while ( v7 );
  }
  if ( v5 )
    LeaveCriticalSection(v5);
  return 0;
}

```

## disassembly

```asm
0x180015fe0  push    rbx
0x180015fe2  push    rbp
0x180015fe3  push    rsi
0x180015fe4  push    rdi
0x180015fe5  push    r12
0x180015fe7  push    r13
0x180015fe9  push    r14
0x180015feb  push    r15
0x180015fed  sub     rsp, 0B8h
0x180015ff4  mov     rax, cs:__security_cookie
0x180015ffb  xor     rax, rsp
0x180015ffe  mov     [rsp+0F8h+var_58], rax
0x180016006  mov     [rsp+0F8h+var_D8], r8d; int
0x18001600b  mov     r13d, edx
0x18001600e  mov     [rsp+0F8h+var_C8], edx
0x180016012  mov     rdi, rcx
0x180016015  lea     rbx, [rcx+20h]
0x180016019  mov     rcx, rbx; lpCriticalSection
0x18001601c  call    cs:__imp_EnterCriticalSection
0x180016022  mov     [rsp+0F8h+var_C0], rbx
0x180016027  mov     rax, [rdi+48h]
0x18001602b  test    rax, rax
0x18001602e  jz      loc_1800160D0
0x180016034  nop     dword ptr [rax+00h]
0x180016038  nop     dword ptr [rax+rax+00000000h]
0x180016040  mov     r14, [rax]
0x180016043  mov     rsi, [rax+10h]
0x180016047  cmp     [rsi+0D4h], r13d
0x18001604e  jnz     short loc_1800160C4
0x180016050  mov     rcx, rbx; lpCriticalSection
0x180016053  call    cs:__imp_EnterCriticalSection
0x180016059  mov     [rsp+0F8h+var_B8], rbx
0x18001605e  lea     r15, [rsi+20h]
0x180016062  mov     rcx, r15; lpCriticalSection
0x180016065  call    cs:__imp_EnterCriticalSection
0x18001606b  mov     [rsp+0F8h+var_B0], r15
0x180016070  mov     rdi, [rsi+48h]
0x180016074  test    rdi, rdi
0x180016077  jz      short loc_1800160A3
0x180016079  mov     r15d, [rsp+0F8h+var_D8]
0x18001607e  lea     r13, off_18004FC98
0x180016085  mov     rbp, [rdi+10h]
0x180016089  mov     rdi, [rdi]
0x18001608c  cmp     dword ptr [rbp+1A0h], 0
0x180016093  jz      short loc_180016104
0x180016095  test    rdi, rdi
0x180016098  jnz     short loc_180016085
0x18001609a  lea     r15, [rsi+20h]
0x18001609e  mov     r13d, [rsp+0F8h+var_C8]
0x1800160a3  mov     rcx, rsi; this
0x1800160a6  call    ?NotifyVolumePolicyChange@CApplication@@IEAAXXZ; CApplication::NotifyVolumePolicyChange(void)
0x1800160ab  nop
0x1800160ac  test    r15, r15
0x1800160af  jz      short loc_1800160BB
0x1800160b1  mov     rcx, r15; lpCriticalSection
0x1800160b4  call    cs:__imp_LeaveCriticalSection
0x1800160ba  nop
0x1800160bb  test    rbx, rbx
0x1800160be  jnz     loc_180016197
0x1800160c4  mov     rax, r14
0x1800160c7  test    r14, r14
0x1800160ca  jnz     loc_180016040
0x1800160d0  test    rbx, rbx
0x1800160d3  jz      short loc_1800160DE
0x1800160d5  mov     rcx, rbx; lpCriticalSection
0x1800160d8  call    cs:__imp_LeaveCriticalSection
0x1800160de  xor     eax, eax
0x1800160e0  mov     rcx, [rsp+0F8h+var_58]
0x1800160e8  xor     rcx, rsp; StackCookie
0x1800160eb  call    __security_check_cookie
0x1800160f0  add     rsp, 0B8h
0x1800160f7  pop     r15
0x1800160f9  pop     r14
0x1800160fb  pop     r13
0x1800160fd  pop     r12
0x1800160ff  pop     rdi
0x180016100  pop     rsi
0x180016101  pop     rbp
0x180016102  pop     rbx
0x180016103  retn
0x180016104  mov     [rsp+0F8h+var_D0], r15d
0x180016109  lea     r12, [rbp+18h]
0x18001610d  mov     rcx, r12; lpCriticalSection
0x180016110  call    cs:__imp_EnterCriticalSection
0x180016116  mov     [rsp+0F8h+var_A8], r12
0x18001611b  mov     [rsp+0F8h+var_98], r13
0x180016120  lea     rax, [rsp+0F8h+var_D0]
0x180016125  mov     [rsp+0F8h+var_90], rax
0x18001612a  lea     rax, [rsp+0F8h+var_98]
0x18001612f  mov     [rsp+0F8h+var_60], rax
0x180016137  lea     rdx, [rsp+0F8h+var_98]
0x18001613c  mov     rcx, rbp
0x18001613f  call    ??$ForEachSession@UIAudioSessionPolicyControl@@@CProcess@@IEAAJ$$QEAV?$function@$$A6AXPEAUIAudioSessionPolicyControl@@PEA_N@Z@std@@@Z; CProcess::ForEachSession<IAudioSessionPolicyControl>(std::function<void (IAudioSessionPolicyControl *,bool *)> &&)
0x180016144  mov     rcx, [rsp+0F8h]; this
0x18001614c  test    eax, eax
0x18001614e  js      short loc_1800161AC
0x180016150  mov     rcx, [rsp+0F8h+var_60]
0x180016158  test    rcx, rcx
0x18001615b  jz      short loc_180016174
0x18001615d  mov     rax, [rcx]
0x180016160  lea     rdx, [rsp+0F8h+var_98]
0x180016165  cmp     rcx, rdx
0x180016168  setnz   dl
0x18001616b  mov     rax, [rax+20h]
0x18001616f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016174  mov     rcx, [rbp+2C0h]; this
0x18001617b  test    rcx, rcx
0x18001617e  jnz     short loc_1800161A5
0x180016180  test    r12, r12
0x180016183  jz      loc_180016095
0x180016189  mov     rcx, r12; lpCriticalSection
0x18001618c  call    cs:__imp_LeaveCriticalSection
0x180016192  jmp     loc_180016095
0x180016197  mov     rcx, rbx; lpCriticalSection
0x18001619a  call    cs:__imp_LeaveCriticalSection
0x1800161a0  jmp     loc_1800160C4
0x1800161a5  call    ?RecalculateVolume@AudioStateMonitorManager@@QEAAJXZ; AudioStateMonitorManager::RecalculateVolume(void)
0x1800161aa  jmp     short loc_180016180
0x1800161ac  mov     r9d, eax; char *
0x1800161af  lea     r8, aClientcoreMult_7; "clientcore\\multimedia\\audiocore\\serv"...
0x1800161b6  mov     edx, 0DA6h; void *
0x1800161bb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800161c0  jmp     short loc_180016150
```
