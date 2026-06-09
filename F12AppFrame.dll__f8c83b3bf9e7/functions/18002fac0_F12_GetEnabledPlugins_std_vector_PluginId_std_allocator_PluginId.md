# F12::GetEnabledPlugins(std::vector<PluginId,std::allocator<PluginId>> &)

- ea: `0x18002fac0`
- end: `0x18002fba1`
- name: `?GetEnabledPlugins@F12@@YAXAEAV?$vector@W4PluginId@@V?$allocator@W4PluginId@@@std@@@std@@@Z`
- size: `225`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18001f024`

## callees

- `0x180020020`
- `0x18002f73c`
- `0x18002f8e4`
- `0x18002fac0`
- `0x18002fe6c`
- `0x1800300c0`
- `0x1800326e8`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18002fb82`
- `KERNEL32!LeaveCriticalSection` at `0x18002fb82`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void **__fastcall F12::GetEnabledPlugins(void **a1)
{
  __int64 v2; // r14
  unsigned __int64 v3; // rdi
  unsigned __int64 i; // rbx
  int *v5; // rsi
  __int64 v6; // rcx
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-58h] BYREF
  char v9; // [rsp+28h] [rbp-50h]
  __int128 v10; // [rsp+30h] [rbp-48h] BYREF
  __int64 v11; // [rsp+40h] [rbp-38h]

  lpCriticalSection = (LPCRITICAL_SECTION)&F12::m_hostHelperMutex;
  v9 = 0;
  ATL::CCritSecLock::Lock((ATL::CCritSecLock *)&lpCriticalSection);
  if ( (void *)qword_1800507E0 == F12::m_plugins )
  {
    v10 = 0;
    v11 = 0;
    F12::GetToolPlugins(&v10);
    v2 = v10;
    v3 = (__int64)(*((_QWORD *)&v10 + 1) - v10) >> 2;
    for ( i = 0; i < v3; ++i )
    {
      v5 = (int *)(v2 + 4 * i);
      if ( F12::IsPluginEnabled(*v5) )
      {
        if ( qword_1800507E0 == qword_1800507E8 )
        {
          std::vector<enum PluginId>::_Emplace_reallocate<enum PluginId const &>(
            v6,
            (_BYTE *)qword_1800507E0,
            (_DWORD *)(v2 + 4 * i));
        }
        else
        {
          *(_DWORD *)qword_1800507E0 = *v5;
          qword_1800507E0 += 4;
        }
      }
    }
    std::vector<enum PluginId>::~vector<enum PluginId>((char **)&v10);
  }
  if ( v9 )
    LeaveCriticalSection(lpCriticalSection);
  return std::vector<enum PluginId>::operator=(a1, (const void **)&F12::m_plugins);
}

```

## disassembly

```asm
0x18002fac0  push    rbx
0x18002fac2  push    rbp
0x18002fac3  push    rsi
0x18002fac4  push    rdi
0x18002fac5  push    r14
0x18002fac7  sub     rsp, 50h
0x18002facb  mov     rbp, rcx
0x18002face  lea     rax, ?m_hostHelperMutex@F12@@3VCComAutoCriticalSection@ATL@@A; ATL::CComAutoCriticalSection F12::m_hostHelperMutex
0x18002fad5  mov     [rsp+78h+lpCriticalSection], rax
0x18002fada  mov     [rsp+78h+var_50], 0
0x18002fadf  lea     rcx, [rsp+78h+lpCriticalSection]; this
0x18002fae4  call    ?Lock@CCritSecLock@ATL@@QEAAXXZ; ATL::CCritSecLock::Lock(void)
0x18002fae9  nop
0x18002faea  mov     rax, cs:qword_1800507E0
0x18002faf1  cmp     rax, cs:?m_plugins@F12@@3V?$vector@W4PluginId@@V?$allocator@W4PluginId@@@std@@@std@@A; std::vector<PluginId> F12::m_plugins
0x18002faf8  jnz     short loc_18002FB76
0x18002fafa  xorps   xmm0, xmm0
0x18002fafd  movdqu  [rsp+78h+var_48], xmm0
0x18002fb03  mov     [rsp+78h+var_38], 0
0x18002fb0c  lea     rcx, [rsp+78h+var_48]
0x18002fb11  call    ?GetToolPlugins@F12@@YAXAEAV?$vector@W4PluginId@@V?$allocator@W4PluginId@@@std@@@std@@@Z; F12::GetToolPlugins(std::vector<PluginId> &)
0x18002fb16  mov     rdi, qword ptr [rsp+78h+var_48+8]
0x18002fb1b  mov     r14, qword ptr [rsp+78h+var_48]
0x18002fb20  sub     rdi, r14
0x18002fb23  sar     rdi, 2
0x18002fb27  xor     ebx, ebx
0x18002fb29  test    rdi, rdi
0x18002fb2c  jz      short loc_18002FB6B
0x18002fb2e  lea     rsi, [r14+rbx*4]
0x18002fb32  mov     ecx, [rsi]
0x18002fb34  call    ?IsPluginEnabled@F12@@YA_NW4PluginId@@@Z; F12::IsPluginEnabled(PluginId)
0x18002fb39  test    al, al
0x18002fb3b  jz      short loc_18002FB63
0x18002fb3d  mov     rdx, cs:qword_1800507E0
0x18002fb44  cmp     rdx, cs:qword_1800507E8
0x18002fb4b  jz      short loc_18002FB5B
0x18002fb4d  mov     eax, [rsi]
0x18002fb4f  mov     [rdx], eax
0x18002fb51  add     cs:qword_1800507E0, 4
0x18002fb59  jmp     short loc_18002FB63
0x18002fb5b  mov     r8, rsi
0x18002fb5e  call    ??$_Emplace_reallocate@AEBW4PluginId@@@?$vector@W4PluginId@@V?$allocator@W4PluginId@@@std@@@std@@AEAAPEAW4PluginId@@QEAW42@AEBW42@@Z; std::vector<PluginId>::_Emplace_reallocate<PluginId const &>(PluginId * const,PluginId const &)
0x18002fb63  inc     rbx
0x18002fb66  cmp     rbx, rdi
0x18002fb69  jb      short loc_18002FB2E
0x18002fb6b  lea     rcx, [rsp+78h+var_48]
0x18002fb70  call    ??1?$vector@W4PluginId@@V?$allocator@W4PluginId@@@std@@@std@@QEAA@XZ; std::vector<PluginId>::~vector<PluginId>(void)
0x18002fb75  nop
0x18002fb76  cmp     [rsp+78h+var_50], 0
0x18002fb7b  jz      short loc_18002FB88
0x18002fb7d  mov     rcx, [rsp+78h+lpCriticalSection]; lpCriticalSection
0x18002fb82  call    cs:__imp_LeaveCriticalSection
0x18002fb88  lea     rdx, ?m_plugins@F12@@3V?$vector@W4PluginId@@V?$allocator@W4PluginId@@@std@@@std@@A; std::vector<PluginId> F12::m_plugins
0x18002fb8f  mov     rcx, rbp
0x18002fb92  add     rsp, 50h
0x18002fb96  pop     r14
0x18002fb98  pop     rdi
0x18002fb99  pop     rsi
0x18002fb9a  pop     rbp
0x18002fb9b  pop     rbx
0x18002fb9c  jmp     ??4?$vector@W4PluginId@@V?$allocator@W4PluginId@@@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<PluginId>::operator=(std::vector<PluginId> const &)
```
