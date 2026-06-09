# JobExecution::AreJobsReady(bool &,bool &)

- ea: `0x140009ea4`
- end: `0x140009f51`
- name: `?AreJobsReady@JobExecution@@SAJAEA_N0@Z`
- size: `173`
- prototype: `__int64 __fastcall(bool *, bool *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140006dc8`

## callees

- `0x140009ea4`
- `0x140011ac4`

## pseudocode

```c
__int64 __fastcall JobExecution::AreJobsReady(bool *a1, bool *a2)
{
  int v2; // r11d
  bool *v3; // r9
  bool *v4; // r10
  __int64 v5; // r8
  __int64 v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 i; // rcx

  v2 = 0;
  v3 = a2;
  *a1 = 0;
  v4 = a1;
  *a2 = 0;
  v5 = 0;
  if ( qword_14002BD68 )
  {
    v6 = *(_QWORD *)JobExecution::m_mapProcessingJobList;
    while ( 1 )
    {
      if ( v6 == JobExecution::m_mapProcessingJobList )
        return (unsigned int)v5;
      if ( v6 == -64 )
      {
        LODWORD(v5) = -2147024882;
        return (unsigned int)v5;
      }
      v7 = *(unsigned int *)(v6 + 220);
      if ( (_DWORD)v7 == 40 || (_DWORD)v7 == 30 )
        goto LABEL_9;
      *v4 = 1;
      if ( *(_DWORD *)(v6 + 424) == v2 )
        break;
LABEL_10:
      if ( *v3 != (_BYTE)v2 )
        return (unsigned int)v5;
LABEL_11:
      if ( *(_BYTE *)(v6 + 25) == (_BYTE)v2 )
      {
        v8 = *(_QWORD *)(v6 + 16);
        if ( *(_BYTE *)(v8 + 25) == (_BYTE)v2 )
        {
          v6 = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,unsigned long>>>::_Min(
                 v8,
                 v7,
                 v5,
                 v3);
        }
        else
        {
          for ( i = *(_QWORD *)(v6 + 8);
                *(_BYTE *)(i + 25) == (_BYTE)v2 && v6 == *(_QWORD *)(i + 16);
                i = *(_QWORD *)(i + 8) )
          {
            v6 = i;
          }
          v6 = i;
        }
      }
    }
    *v3 = 1;
LABEL_9:
    if ( *v4 == (_BYTE)v2 )
      goto LABEL_11;
    goto LABEL_10;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140009ea4  sub     rsp, 28h
0x140009ea8  xor     r11d, r11d
0x140009eab  mov     r9, rdx
0x140009eae  mov     [rcx], r11b
0x140009eb1  mov     r10, rcx
0x140009eb4  mov     [rdx], r11b
0x140009eb7  mov     r8d, r11d
0x140009eba  cmp     cs:qword_14002BD68, r11
0x140009ec1  jz      loc_140009F49
0x140009ec7  mov     rax, cs:?m_mapProcessingJobList@JobExecution@@0V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_Job@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_Job@@@std@@@2@@std@@A; std::map<std::wstring,_Job> JobExecution::m_mapProcessingJobList
0x140009ece  mov     rax, [rax]
0x140009ed1  cmp     rax, cs:?m_mapProcessingJobList@JobExecution@@0V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_Job@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_Job@@@std@@@2@@std@@A; std::map<std::wstring,_Job> JobExecution::m_mapProcessingJobList
0x140009ed8  jz      short loc_140009F49
0x140009eda  lea     rcx, [rax+40h]
0x140009ede  test    rcx, rcx
0x140009ee1  jz      short loc_140009F43
0x140009ee3  mov     edx, [rcx+9Ch]
0x140009ee9  cmp     edx, 28h ; '('
0x140009eec  jz      short loc_140009F04
0x140009eee  cmp     edx, 1Eh
0x140009ef1  jz      short loc_140009F04
0x140009ef3  mov     byte ptr [r10], 1
0x140009ef7  cmp     [rcx+168h], r11d
0x140009efe  jnz     short loc_140009F09
0x140009f00  mov     byte ptr [r9], 1
0x140009f04  cmp     [r10], r11b
0x140009f07  jz      short loc_140009F0E
0x140009f09  cmp     [r9], r11b
0x140009f0c  jnz     short loc_140009F49
0x140009f0e  cmp     [rax+19h], r11b
0x140009f12  jnz     short loc_140009ED1
0x140009f14  mov     rcx, [rax+10h]
0x140009f18  cmp     [rcx+19h], r11b
0x140009f1c  jnz     short loc_140009F25
0x140009f1e  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,ulong>>>::_Min(std::_Tree_node<std::pair<std::wstring const,ulong>,void *> *)
0x140009f23  jmp     short loc_140009ED1
0x140009f25  mov     rcx, [rax+8]
0x140009f29  jmp     short loc_140009F38
0x140009f2b  cmp     rax, [rcx+10h]
0x140009f2f  jnz     short loc_140009F3E
0x140009f31  mov     rax, rcx
0x140009f34  mov     rcx, [rcx+8]
0x140009f38  cmp     [rcx+19h], r11b
0x140009f3c  jz      short loc_140009F2B
0x140009f3e  mov     rax, rcx
0x140009f41  jmp     short loc_140009ED1
0x140009f43  mov     r8d, 8007000Eh
0x140009f49  mov     eax, r8d
0x140009f4c  add     rsp, 28h
0x140009f50  retn
```
