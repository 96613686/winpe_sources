# tip2::test_watcher<tip2::details::merged_data<AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest,AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest>>::~test_watcher<tip2::details::merged_data<AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest,AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest>>(void)

- ea: `0x180007e10`
- end: `0x180007e95`
- name: `??1?$test_watcher@V?$merged_data@U_tip_ModelCacheManagerPackageCacheGenerationTest@AIFabricTipTest@@U12@@details@tip2@@@tip2@@QEAA@XZ`
- size: `133`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001dfb0`

## callees

- `0x180007e10`
- `0x180009e10`
- `0x180010c70`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180007e39`
- `KERNEL32!GetCurrentThreadId` at `0x180007e39`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall tip2::test_watcher<tip2::details::merged_data<AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest,AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest>>::~test_watcher<tip2::details::merged_data<AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest,AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest>>(
        __int64 a1)
{
  void *v2; // rcx
  __int64 v3; // rdi
  int v4; // ebx
  void *v5; // rdx
  unsigned int v6; // r8d
  __int64 *v7; // rcx
  __int64 v8; // rax
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = *(void **)(a1 + 48);
  if ( v2 )
    tip2::details::merged_data<AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest,AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest>::Release(v2);
  v3 = a1 + 8;
  if ( *(_DWORD *)(v3 + 24) )
  {
    v4 = *(_DWORD *)(v3 + 24);
    if ( v4 != GetCurrentThreadId() )
      wil::details::in1diag3::Log_Hr(retaddr, v5, v6, (const char *)0x8007029CLL, v9);
    v7 = *(__int64 **)v3;
    *(_DWORD *)(v3 + 24) = 0;
    v8 = *v7;
    if ( *v7 )
    {
      while ( v8 != v3 )
      {
        v7 = (__int64 *)(v8 + 16);
        *(_QWORD *)v3 = v8 + 16;
        v8 = *(_QWORD *)(v8 + 16);
        if ( !v8 )
        {
          *(_QWORD *)v3 = 0;
          return;
        }
      }
      *v7 = *(_QWORD *)(v3 + 16);
    }
    *(_QWORD *)v3 = 0;
  }
}

```

## disassembly

```asm
0x180007e10  push    rdi; int
0x180007e12  sub     rsp, 20h
0x180007e16  mov     rdi, rcx
0x180007e19  mov     rcx, [rcx+30h]; pv
0x180007e1d  test    rcx, rcx
0x180007e20  jz      short loc_180007E27
0x180007e22  call    ?Release@?$merged_data@U_tip_ModelCacheManagerPackageCacheGenerationTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest,AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest>::Release(void)
0x180007e27  add     rdi, 8
0x180007e2b  cmp     dword ptr [rdi+18h], 0
0x180007e2f  jz      short loc_180007E8F
0x180007e31  mov     [rsp+28h+arg_0], rbx
0x180007e36  mov     ebx, [rdi+18h]
0x180007e39  call    cs:__imp_GetCurrentThreadId
0x180007e3f  cmp     ebx, eax
0x180007e41  mov     rbx, [rsp+28h+arg_0]
0x180007e46  jz      short loc_180007E58
0x180007e48  mov     rcx, [rsp+28h]; this
0x180007e4d  mov     r9d, 8007029Ch; char *
0x180007e53  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180007e58  mov     rcx, [rdi]
0x180007e5b  xor     edx, edx
0x180007e5d  mov     [rdi+18h], edx
0x180007e60  mov     rax, [rcx]
0x180007e63  test    rax, rax
0x180007e66  jz      short loc_180007E8C
0x180007e68  cmp     rax, rdi
0x180007e6b  jz      short loc_180007E85
0x180007e6d  lea     rcx, [rax+10h]
0x180007e71  mov     [rdi], rcx
0x180007e74  mov     rax, [rcx]
0x180007e77  test    rax, rax
0x180007e7a  jnz     short loc_180007E68
0x180007e7c  mov     [rdi], rdx
0x180007e7f  add     rsp, 20h
0x180007e83  pop     rdi
0x180007e84  retn
0x180007e85  mov     rax, [rdi+10h]
0x180007e89  mov     [rcx], rax
0x180007e8c  mov     [rdi], rdx
0x180007e8f  add     rsp, 20h
0x180007e93  pop     rdi
0x180007e94  retn
```
