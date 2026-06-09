# std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>,0>>::_Clear_guard::~_Clear_guard(void)

- ea: `0x18001282c`
- end: `0x1800128e2`
- name: `??1_Clear_guard@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@QEAA@XZ`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180021eac`

## callees

- `0x18000282c`
- `0x18001282c`
- `0x180022304`

## pseudocode

```c
void __fastcall std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>,0>>::_Clear_guard::~_Clear_guard(
        unsigned __int64 **a1)
{
  unsigned __int64 *v1; // rbx
  unsigned __int64 v2; // rcx
  _QWORD *v3; // rcx
  _QWORD *v4; // rdi
  void *v5; // rdi
  unsigned __int64 v6; // rcx

  v1 = *a1;
  if ( *a1 && v1[2] )
  {
    v2 = v1[1];
    if ( v1[7] >> 3 <= v1[2] )
    {
      **(_QWORD **)(v2 + 8) = 0;
      v3 = *(_QWORD **)v2;
      if ( v3 )
      {
        do
        {
          v4 = (_QWORD *)*v3;
          operator delete(v3);
          v3 = v4;
        }
        while ( v4 );
      }
      *(_QWORD *)v1[1] = v1[1];
      *(_QWORD *)(v1[1] + 8) = v1[1];
      v1[2] = 0;
      v5 = (void *)v1[3];
      v6 = (v1[4] - (unsigned __int64)v5 + 7) >> 3;
      if ( (unsigned __int64)v5 > v1[4] )
        v6 = 0;
      if ( v6 )
        memset64(v5, v1[1], v6);
    }
    else
    {
      std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>,0>>::_Unchecked_erase(
        v1,
        *(_QWORD *)v2,
        v1[1]);
    }
  }
}

```

## disassembly

```asm
0x18001282c  mov     [rsp+arg_0], rbx
0x180012831  push    rdi
0x180012832  sub     rsp, 20h
0x180012836  mov     rbx, [rcx]
0x180012839  test    rbx, rbx
0x18001283c  jz      loc_1800128D7
0x180012842  cmp     qword ptr [rbx+10h], 0
0x180012847  jz      loc_1800128D7
0x18001284d  mov     rax, [rbx+38h]
0x180012851  mov     rcx, [rbx+8]
0x180012855  shr     rax, 3
0x180012859  cmp     rax, [rbx+10h]
0x18001285d  jbe     short loc_18001286F
0x18001285f  mov     rdx, [rcx]
0x180012862  mov     r8, rcx
0x180012865  mov     rcx, rbx
0x180012868  call    ?_Unchecked_erase@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@AEAAPEAU?$_List_node@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@PEAX@2@PEAU32@QEAU32@@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>,0>>::_Unchecked_erase(std::_List_node<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *,void *> *,std::_List_node<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *,void *> * const)
0x18001286d  jmp     short loc_1800128D7
0x18001286f  mov     rax, [rcx+8]
0x180012873  mov     qword ptr [rax], 0
0x18001287a  mov     rcx, [rcx]; Block
0x18001287d  test    rcx, rcx
0x180012880  jz      short loc_180012897
0x180012882  mov     rdi, [rcx]
0x180012885  mov     edx, 18h
0x18001288a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001288f  mov     rcx, rdi
0x180012892  test    rdi, rdi
0x180012895  jnz     short loc_180012882
0x180012897  mov     rax, [rbx+8]
0x18001289b  xor     edx, edx
0x18001289d  mov     [rax], rax
0x1800128a0  mov     rax, [rbx+8]
0x1800128a4  mov     [rax+8], rax
0x1800128a8  mov     qword ptr [rbx+10h], 0
0x1800128b0  mov     rdi, [rbx+18h]
0x1800128b4  mov     rcx, [rbx+20h]
0x1800128b8  sub     rcx, rdi
0x1800128bb  add     rcx, 7
0x1800128bf  shr     rcx, 3
0x1800128c3  cmp     rdi, [rbx+20h]
0x1800128c7  cmova   rcx, rdx
0x1800128cb  test    rcx, rcx
0x1800128ce  jz      short loc_1800128D7
0x1800128d0  mov     rax, [rbx+8]
0x1800128d4  rep stosq
0x1800128d7  mov     rbx, [rsp+28h+arg_0]
0x1800128dc  add     rsp, 20h
0x1800128e0  pop     rdi
0x1800128e1  retn
```
