# _SwJob::~_SwJob(void)

- ea: `0x18000bd00`
- end: `0x18000bd69`
- name: `??1_SwJob@@QEAA@XZ`
- size: `105`
- prototype: `void __fastcall(_SwJob *__hidden this)`
- caller_count: `33`
- callee_count: `4`
- tags: ``

## callers

- `0x18000c588`
- `0x18000c734`
- `0x18000cb4c`
- `0x18000ccb4`
- `0x18000d2cc`
- `0x18000da10`
- `0x18000dcb4`
- `0x18000fa44`
- `0x18000fe4c`
- `0x1800100a4`
- `0x1800102b8`
- `0x180010700`
- `0x180010eac`
- `0x180012a88`
- `0x1800182b4`
- `0x180019f78`
- `0x18001a2c8`
- `0x1800201df`
- `0x180020227`
- `0x18002024b`
- `0x18002025d`
- `0x180020293`
- `0x180020311`
- `0x180020323`
- `0x180020477`
- `0x18002049b`
- `0x1800204bf`
- `0x1800204d1`
- `0x18002052b`
- `0x18002053d`
- `0x18002054f`
- `0x180020a31`
- `0x180020af7`

## callees

- `0x1800062ac`
- `0x18000707c`
- `0x18000b9b8`
- `0x18000bc8c`

## pseudocode

```c
void __fastcall _SwJob::~_SwJob(_SwJob *this)
{
  __int64 v2; // rdx
  __int64 v3; // rdx
  __int64 v4; // rdx
  __int64 v5; // rdx

  std::_Tree<std::_Tmap_traits<std::wstring,_FrameworkDependency,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_FrameworkDependency>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,_FrameworkDependency,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_FrameworkDependency>>,0>>((char *)this + 304);
  _DownloadProgress::~_DownloadProgress((_SwJob *)((char *)this + 192));
  LOBYTE(v2) = 1;
  std::wstring::_Tidy((char *)this + 160, v2, 0);
  LOBYTE(v3) = 1;
  std::wstring::_Tidy((char *)this + 112, v3, 0);
  std::list<std::wstring>::~list<std::wstring>((char *)this + 80);
  LOBYTE(v4) = 1;
  std::wstring::_Tidy((char *)this + 32, v4, 0);
  LOBYTE(v5) = 1;
  std::wstring::_Tidy(this, v5, 0);
}

```

## disassembly

```asm
0x18000bd00  push    rbx
0x18000bd02  sub     rsp, 20h
0x18000bd06  mov     rbx, rcx
0x18000bd09  add     rcx, 130h
0x18000bd10  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FrameworkDependency@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FrameworkDependency@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,_FrameworkDependency,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_FrameworkDependency>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,_FrameworkDependency,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_FrameworkDependency>>,0>>(void)
0x18000bd15  lea     rcx, [rbx+0C0h]; this
0x18000bd1c  call    ??1_DownloadProgress@@QEAA@XZ; _DownloadProgress::~_DownloadProgress(void)
0x18000bd21  lea     rcx, [rbx+0A0h]
0x18000bd28  xor     r8d, r8d
0x18000bd2b  mov     dl, 1
0x18000bd2d  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000bd32  lea     rcx, [rbx+70h]
0x18000bd36  xor     r8d, r8d
0x18000bd39  mov     dl, 1
0x18000bd3b  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000bd40  lea     rcx, [rbx+50h]
0x18000bd44  call    ??1?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::~list<std::wstring>(void)
0x18000bd49  lea     rcx, [rbx+20h]
0x18000bd4d  xor     r8d, r8d
0x18000bd50  mov     dl, 1
0x18000bd52  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000bd57  xor     r8d, r8d
0x18000bd5a  mov     dl, 1
0x18000bd5c  mov     rcx, rbx
0x18000bd5f  add     rsp, 20h
0x18000bd63  pop     rbx
0x18000bd64  jmp     ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
```
