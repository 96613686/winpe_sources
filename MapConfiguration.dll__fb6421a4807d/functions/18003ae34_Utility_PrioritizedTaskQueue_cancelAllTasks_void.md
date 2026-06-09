# Utility::PrioritizedTaskQueue::cancelAllTasks(void)

- ea: `0x18003ae34`
- end: `0x18003af1e`
- name: `?cancelAllTasks@PrioritizedTaskQueue@Utility@@QEAAXXZ`
- size: `234`
- prototype: `void __fastcall(Utility::PrioritizedTaskQueue *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001f774`
- `0x18003aad8`

## callees

- `0x18000b938`
- `0x18000cb0c`
- `0x18001a79c`
- `0x18001c0f0`
- `0x18001d758`
- `0x180029eb8`
- `0x18003ae34`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ae5e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ae5e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003aebb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003aebb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Utility::PrioritizedTaskQueue::cancelAllTasks(Utility::PrioritizedTaskQueue *this, __int64 a2)
{
  void **v3; // rdx
  Pal::Task **v4; // rax
  Pal::Task **v5; // rdi
  __int64 v6; // rax
  __int64 v7; // rbp
  __int64 v8; // rax
  __int64 v9; // rbx
  Pal::Task **i; // rsi
  Pal::Task **v11; // [rsp+20h] [rbp-58h] BYREF
  __int64 v12; // [rsp+28h] [rbp-50h]
  __int64 v13; // [rsp+30h] [rbp-48h]

  LOBYTE(a2) = 1;
  std::_Atomic_storage<bool,1>::store((char *)this + 88, a2);
  std::vector<std::map<enum MapControl::ConfigurationKeys,std::wstring>>::vector<std::map<enum MapControl::ConfigurationKeys,std::wstring>>(&v11);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v3 = (void **)((char *)this + 64);
  if ( &v11 == (Pal::Task ***)((char *)this + 64) )
  {
    v9 = v13;
    v7 = v12;
    v5 = v11;
  }
  else
  {
    v4 = v11;
    v5 = (Pal::Task **)*v3;
    v11 = (Pal::Task **)*v3;
    *v3 = v4;
    v6 = v12;
    v7 = *((_QWORD *)this + 9);
    v12 = v7;
    *((_QWORD *)this + 9) = v6;
    v8 = v13;
    v9 = *((_QWORD *)this + 10);
    v13 = v9;
    *((_QWORD *)this + 10) = v8;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  for ( i = v5; i != (Pal::Task **)v7; i += 2 )
    Pal::Task::cancel(*i);
  Pal::TaskQueue::cancelAllTasks((Utility::PrioritizedTaskQueue *)((char *)this + 16));
  std::_Atomic_storage<bool,1>::store((char *)this + 88, 0);
  if ( v5 )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<Utility::PrioritizableTask>>>((__int64)v5, v7);
    std::_Deallocate<16>(v5, (v9 - (_QWORD)v5) & 0xFFFFFFFFFFFFFFF0uLL);
  }
}

```

## disassembly

```asm
0x18003ae34  push    rbx
0x18003ae36  push    rbp
0x18003ae37  push    rsi
0x18003ae38  push    rdi
0x18003ae39  push    r14
0x18003ae3b  push    r15
0x18003ae3d  sub     rsp, 48h
0x18003ae41  mov     r14, rcx
0x18003ae44  mov     dl, 1
0x18003ae46  add     rcx, 58h ; 'X'
0x18003ae4a  call    ?store@?$_Atomic_storage@_N$00@std@@QEAAX_NW4memory_order@2@@Z; std::_Atomic_storage<bool,1>::store(bool,std::memory_order)
0x18003ae4f  lea     rcx, [rsp+78h+var_58]
0x18003ae54  call    ??0?$vector@V?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@std@@V?$allocator@V?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@std@@@2@@std@@QEAA@XZ; std::vector<std::map<MapControl::ConfigurationKeys,std::wstring>>::vector<std::map<MapControl::ConfigurationKeys,std::wstring>>(void)
0x18003ae59  nop
0x18003ae5a  lea     rcx, [r14+18h]; lpCriticalSection
0x18003ae5e  call    cs:__imp_EnterCriticalSection
0x18003ae64  lea     rdx, [r14+40h]
0x18003ae68  lea     rax, [rsp+78h+var_58]
0x18003ae6d  cmp     rax, rdx
0x18003ae70  jz      short loc_18003AEA8
0x18003ae72  mov     rax, [rsp+78h+var_58]
0x18003ae77  mov     rdi, [rdx]
0x18003ae7a  mov     [rsp+78h+var_58], rdi
0x18003ae7f  mov     [rdx], rax
0x18003ae82  mov     rax, [rsp+78h+var_50]
0x18003ae87  mov     rbp, [rdx+8]
0x18003ae8b  mov     [rsp+78h+var_50], rbp
0x18003ae90  mov     [rdx+8], rax
0x18003ae94  mov     rax, [rsp+78h+var_48]
0x18003ae99  mov     rbx, [rdx+10h]
0x18003ae9d  mov     [rsp+78h+var_48], rbx
0x18003aea2  mov     [rdx+10h], rax
0x18003aea6  jmp     short loc_18003AEB7
0x18003aea8  mov     rbx, [rsp+78h+var_48]
0x18003aead  mov     rbp, [rsp+78h+var_50]
0x18003aeb2  mov     rdi, [rsp+78h+var_58]
0x18003aeb7  lea     rcx, [r14+18h]; lpCriticalSection
0x18003aebb  call    cs:__imp_LeaveCriticalSection
0x18003aec1  mov     rsi, rdi
0x18003aec4  cmp     rdi, rbp
0x18003aec7  jz      short loc_18003AEDA
0x18003aec9  mov     rcx, [rsi]; this
0x18003aecc  call    ?cancel@Task@Pal@@UEAA_NXZ; Pal::Task::cancel(void)
0x18003aed1  add     rsi, 10h
0x18003aed5  cmp     rsi, rbp
0x18003aed8  jnz     short loc_18003AEC9
0x18003aeda  lea     rcx, [r14+10h]; this
0x18003aede  call    ?cancelAllTasks@TaskQueue@Pal@@QEAAXXZ; Pal::TaskQueue::cancelAllTasks(void)
0x18003aee3  xor     edx, edx
0x18003aee5  lea     rcx, [r14+58h]
0x18003aee9  call    ?store@?$_Atomic_storage@_N$00@std@@QEAAX_NW4memory_order@2@@Z; std::_Atomic_storage<bool,1>::store(bool,std::memory_order)
0x18003aeee  nop
0x18003aeef  test    rdi, rdi
0x18003aef2  jz      short loc_18003AF11
0x18003aef4  mov     rdx, rbp
0x18003aef7  mov     rcx, rdi
0x18003aefa  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VPrioritizableTask@Utility@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VPrioritizableTask@Utility@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VPrioritizableTask@Utility@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<Utility::PrioritizableTask>>>(std::shared_ptr<Utility::PrioritizableTask> *,std::shared_ptr<Utility::PrioritizableTask> * const,std::allocator<std::shared_ptr<Utility::PrioritizableTask>> &)
0x18003aeff  sub     rbx, rdi
0x18003af02  and     rbx, 0FFFFFFFFFFFFFFF0h
0x18003af06  mov     rdx, rbx
0x18003af09  mov     rcx, rdi
0x18003af0c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18003af11  add     rsp, 48h
0x18003af15  pop     r15
0x18003af17  pop     r14
0x18003af19  pop     rdi
0x18003af1a  pop     rsi
0x18003af1b  pop     rbp
0x18003af1c  pop     rbx
0x18003af1d  retn
```
