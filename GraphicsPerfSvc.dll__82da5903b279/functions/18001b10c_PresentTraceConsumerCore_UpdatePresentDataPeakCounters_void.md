# PresentTraceConsumerCore::UpdatePresentDataPeakCounters(void)

- ea: `0x18001b10c`
- end: `0x18001b30d`
- name: `?UpdatePresentDataPeakCounters@PresentTraceConsumerCore@@QEAAXXZ`
- size: `513`
- prototype: `void __fastcall(PresentTraceConsumerCore *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x18001a580`

## callees

- `0x180003ab0`
- `0x180003ebc`
- `0x18000d778`
- `0x180011fe0`
- `0x180012004`
- `0x1800171c8`
- `0x180017f9c`
- `0x18001b10c`
- `0x180022dec`
- `0x180022e90`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001b21f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001b21f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall PresentTraceConsumerCore::UpdatePresentDataPeakCounters(PresentTraceConsumerCore *this)
{
  _QWORD *v2; // rax
  unsigned __int64 v3; // r14
  __int64 *v4; // rbx
  __int64 v5; // rdi
  __int64 v6; // rax
  __int64 **v7; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  __int64 *v10; // rbx
  char *v11; // rdi
  int ProcessTelemetryAppSessionGuid; // eax
  __int64 ProcessName; // rax
  __int64 **v14; // rcx
  __int64 *k; // rax
  __int64 *m; // rcx
  char *v17; // [rsp+20h] [rbp-48h] BYREF
  __int128 v18; // [rsp+28h] [rbp-40h] BYREF
  struct _GUID v19; // [rsp+38h] [rbp-30h] BYREF

  v18 = 0;
  v2 = operator new(0x30u);
  *v2 = v2;
  v2[1] = v2;
  v2[2] = v2;
  *((_WORD *)v2 + 12) = 257;
  *(_QWORD *)&v18 = v2;
  v3 = 0;
  v4 = **(__int64 ***)(*((_QWORD *)this + 33) + 432LL);
  while ( !*((_BYTE *)v4 + 25) )
  {
    v5 = v4[6];
    v3 += v5;
    LODWORD(v17) = *((_DWORD *)v4 + 8);
    v6 = std::map<unsigned long,unsigned __int64>::_Try_emplace<unsigned long,>(&v18, &v19, &v17);
    *(_QWORD *)(*(_QWORD *)v6 + 40LL) += v5;
    v7 = (__int64 **)v4[2];
    if ( *((_BYTE *)v7 + 25) )
    {
      for ( i = (__int64 *)v4[1]; !*((_BYTE *)i + 25) && v4 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v4 = i;
      v4 = i;
    }
    else
    {
      v4 = (__int64 *)v4[2];
      for ( j = *v7; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v4 = j;
    }
  }
  *((_QWORD *)this + 53) = v3;
  if ( v3 > *((_QWORD *)this + 54) )
    *((_QWORD *)this + 54) = v3;
  v10 = *(__int64 **)v18;
  while ( !*((_BYTE *)v10 + 25) )
  {
    if ( *((_QWORD *)this + 55) < (unsigned __int64)v10[5] )
    {
      v11 = (char *)OpenProcess(0x1000u, 0, *((_DWORD *)v10 + 8));
      v17 = v11;
      if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        v19 = GUID_NULL;
        ProcessTelemetryAppSessionGuid = GetProcessTelemetryAppSessionGuid(v11, &v19);
        *((_DWORD *)this + 124) = ProcessTelemetryAppSessionGuid;
        if ( ProcessTelemetryAppSessionGuid >= 0 )
          *((struct _GUID *)this + 30) = v19;
        *((_QWORD *)this + 55) = v10[5];
        ProcessName = GetProcessName(&v19, v11);
        std::string::operator=((char *)this + 448, ProcessName);
        std::string::_Tidy_deallocate((__int64)&v19);
      }
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v17);
    }
    v14 = (__int64 **)v10[2];
    if ( *((_BYTE *)v14 + 25) )
    {
      for ( k = (__int64 *)v10[1]; !*((_BYTE *)k + 25) && v10 == (__int64 *)k[2]; k = (__int64 *)k[1] )
        v10 = k;
      v10 = k;
    }
    else
    {
      v10 = (__int64 *)v10[2];
      for ( m = *v14; !*((_BYTE *)m + 25); m = (__int64 *)*m )
        v10 = m;
    }
  }
  std::_Tree<std::_Tmap_traits<unsigned __int64,unsigned __int64,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<unsigned __int64,unsigned __int64,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,unsigned __int64>>,0>>(&v18);
}

```

## disassembly

```asm
0x18001b10c  push    rbp
0x18001b10e  push    rbx
0x18001b10f  push    rsi
0x18001b110  push    rdi
0x18001b111  push    r14
0x18001b113  push    r15
0x18001b115  mov     rbp, rsp
0x18001b118  sub     rsp, 68h
0x18001b11c  mov     rax, cs:__security_cookie
0x18001b123  xor     rax, rsp
0x18001b126  mov     [rbp+var_10], rax
0x18001b12a  mov     rsi, rcx
0x18001b12d  xorps   xmm0, xmm0
0x18001b130  movdqu  [rbp+var_40], xmm0
0x18001b135  mov     ecx, 30h ; '0'; Size
0x18001b13a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b13f  mov     [rax], rax
0x18001b142  mov     [rax+8], rax
0x18001b146  mov     [rax+10h], rax
0x18001b14a  mov     word ptr [rax+18h], 101h
0x18001b150  mov     qword ptr [rbp+var_40], rax
0x18001b154  xor     r15d, r15d
0x18001b157  mov     r14d, r15d
0x18001b15a  mov     rax, [rsi+108h]
0x18001b161  mov     rbx, [rax+1B0h]
0x18001b168  mov     rbx, [rbx]
0x18001b16b  cmp     [rbx+19h], r15b
0x18001b16f  jnz     short loc_18001B1DB
0x18001b171  mov     rdi, [rbx+30h]
0x18001b175  add     r14, rdi
0x18001b178  mov     eax, [rbx+20h]
0x18001b17b  mov     dword ptr [rbp+var_48], eax
0x18001b17e  lea     r8, [rbp+var_48]
0x18001b182  lea     rdx, [rbp+var_30]
0x18001b186  lea     rcx, [rbp+var_40]
0x18001b18a  call    ??$_Try_emplace@K$$V@?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBK_K@std@@PEAX@std@@_N@1@$$QEAK@Z; std::map<ulong,unsigned __int64>::_Try_emplace<ulong,>(ulong &&)
0x18001b18f  mov     rcx, [rax]
0x18001b192  add     [rcx+28h], rdi
0x18001b196  mov     rcx, [rbx+10h]
0x18001b19a  cmp     [rcx+19h], r15b
0x18001b19e  jz      short loc_18001B1BE
0x18001b1a0  mov     rax, [rbx+8]
0x18001b1a4  jmp     short loc_18001B1B3
0x18001b1a6  cmp     rbx, [rax+10h]
0x18001b1aa  jnz     short loc_18001B1B9
0x18001b1ac  mov     rbx, rax
0x18001b1af  mov     rax, [rax+8]
0x18001b1b3  cmp     [rax+19h], r15b
0x18001b1b7  jz      short loc_18001B1A6
0x18001b1b9  mov     rbx, rax
0x18001b1bc  jmp     short loc_18001B16B
0x18001b1be  mov     rbx, rcx
0x18001b1c1  mov     rcx, [rcx]
0x18001b1c4  cmp     [rcx+19h], r15b
0x18001b1c8  jnz     short loc_18001B16B
0x18001b1ca  mov     rbx, rcx
0x18001b1cd  mov     rax, [rcx]
0x18001b1d0  mov     rcx, rax
0x18001b1d3  cmp     [rax+19h], r15b
0x18001b1d7  jz      short loc_18001B1CA
0x18001b1d9  jmp     short loc_18001B16B
0x18001b1db  mov     [rsi+1A8h], r14
0x18001b1e2  cmp     r14, [rsi+1B0h]
0x18001b1e9  jbe     short loc_18001B1F2
0x18001b1eb  mov     [rsi+1B0h], r14
0x18001b1f2  mov     rbx, qword ptr [rbp+var_40]
0x18001b1f6  mov     rbx, [rbx]
0x18001b1f9  cmp     [rbx+19h], r15b
0x18001b1fd  jnz     loc_18001B2EB
0x18001b203  mov     rax, [rbx+28h]
0x18001b207  cmp     [rsi+1B8h], rax
0x18001b20e  jnb     loc_18001B29C
0x18001b214  mov     r8d, [rbx+20h]; dwProcessId
0x18001b218  xor     edx, edx; bInheritHandle
0x18001b21a  mov     ecx, 1000h; dwDesiredAccess
0x18001b21f  call    cs:__imp_OpenProcess
0x18001b225  mov     rdi, rax
0x18001b228  mov     [rbp+var_48], rax
0x18001b22c  dec     rax
0x18001b22f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001b233  ja      short loc_18001B293
0x18001b235  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18001b23c  movdqu  xmmword ptr [rbp+var_30.Data1], xmm0
0x18001b241  lea     rdx, [rbp+var_30]; struct _GUID *
0x18001b245  mov     rcx, rdi; ProcessHandle
0x18001b248  call    ?GetProcessTelemetryAppSessionGuid@@YAJPEAXPEAU_GUID@@@Z; GetProcessTelemetryAppSessionGuid(void *,_GUID *)
0x18001b24d  mov     [rsi+1F0h], eax
0x18001b253  test    eax, eax
0x18001b255  js      short loc_18001B263
0x18001b257  movups  xmm0, xmmword ptr [rbp+var_30.Data1]
0x18001b25b  movdqu  xmmword ptr [rsi+1E0h], xmm0
0x18001b263  mov     rax, [rbx+28h]
0x18001b267  mov     [rsi+1B8h], rax
0x18001b26e  mov     rdx, rdi
0x18001b271  lea     rcx, [rbp+var_30]
0x18001b275  call    ?GetProcessName@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAX@Z; GetProcessName(void *)
0x18001b27a  lea     rcx, [rsi+1C0h]
0x18001b281  mov     rdx, rax
0x18001b284  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x18001b289  lea     rcx, [rbp+var_30]
0x18001b28d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18001b292  nop
0x18001b293  lea     rcx, [rbp+var_48]
0x18001b297  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001b29c  mov     rcx, [rbx+10h]
0x18001b2a0  cmp     [rcx+19h], r15b
0x18001b2a4  jz      short loc_18001B2C7
0x18001b2a6  mov     rax, [rbx+8]
0x18001b2aa  jmp     short loc_18001B2B9
0x18001b2ac  cmp     rbx, [rax+10h]
0x18001b2b0  jnz     short loc_18001B2BF
0x18001b2b2  mov     rbx, rax
0x18001b2b5  mov     rax, [rax+8]
0x18001b2b9  cmp     [rax+19h], r15b
0x18001b2bd  jz      short loc_18001B2AC
0x18001b2bf  mov     rbx, rax
0x18001b2c2  jmp     loc_18001B1F9
0x18001b2c7  mov     rbx, rcx
0x18001b2ca  mov     rcx, [rcx]
0x18001b2cd  cmp     [rcx+19h], r15b
0x18001b2d1  jnz     loc_18001B1F9
0x18001b2d7  mov     rbx, rcx
0x18001b2da  mov     rax, [rcx]
0x18001b2dd  mov     rcx, rax
0x18001b2e0  cmp     [rax+19h], r15b
0x18001b2e4  jz      short loc_18001B2D7
0x18001b2e6  jmp     loc_18001B1F9
0x18001b2eb  lea     rcx, [rbp+var_40]
0x18001b2ef  call    ??1?$_Tree@V?$_Tmap_traits@_K_KU?$less@_K@std@@V?$allocator@U?$pair@$$CB_K_K@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<unsigned __int64,unsigned __int64,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<unsigned __int64,unsigned __int64,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,unsigned __int64>>,0>>(void)
0x18001b2f4  mov     rcx, [rbp+var_10]
0x18001b2f8  xor     rcx, rsp; StackCookie
0x18001b2fb  call    __security_check_cookie
0x18001b300  add     rsp, 68h
0x18001b304  pop     r15
0x18001b306  pop     r14
0x18001b308  pop     rdi
0x18001b309  pop     rsi
0x18001b30a  pop     rbx
0x18001b30b  pop     rbp
0x18001b30c  retn
```
