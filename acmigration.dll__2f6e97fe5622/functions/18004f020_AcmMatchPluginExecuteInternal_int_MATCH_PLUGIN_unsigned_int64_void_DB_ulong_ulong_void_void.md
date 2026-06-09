# AcmMatchPluginExecuteInternal(int *,_MATCH_PLUGIN * *,unsigned __int64,void *,_DB *,ulong,ulong,void *,void *)

- ea: `0x18004f020`
- end: `0x18004f234`
- name: `?AcmMatchPluginExecuteInternal@@YAJPEAHPEAPEAU_MATCH_PLUGIN@@_KPEAXPEAU_DB@@KK33@Z`
- size: `532`
- prototype: `__int64 __fastcall(int *, struct _MATCH_PLUGIN **, unsigned __int64, void *, struct _DB *, unsigned int, unsigned int, void *, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004eaa0`

## callees

- `0x180002790`
- `0x18004f020`
- `0x1800543c0`
- `0x18005da34`
- `0x18005db74`
- `0x18006a010`

## string_xrefs

- `0x18004f137`: `AcmMatchPluginExecuteInternal`
- `0x18004f176`: `AcmMatchPluginExecuteInternal`
- `0x18004f1d9`: `AcmMatchPluginExecuteInternal`
- `0x18004f210`: `AcmMatchPluginExecuteInternal`
- `0x18004f086`: `Failed to find plugin name.`
- `0x18004f0ad`: `Failed to read plugin name.`
- `0x18004f0eb`: `Failed to read plugin command line.`
- `0x18004f125`: `Plugin not registered [%ls].`
- `0x18004f164`: `Plugin has a PluginContext set [%ls].`
- `0x18004f1c7`: `Plugin returned failure [%ls: %ls]`

## pseudocode

```c
__int64 __fastcall AcmMatchPluginExecuteInternal(
        int *a1,
        struct _MATCH_PLUGIN **a2,
        __int64 a3,
        void *a4,
        struct _DB *a5,
        unsigned int a6,
        unsigned int a7,
        void *a8,
        struct _MATCH_PLUGIN *a9)
{
  struct _DB *v11; // rbx
  unsigned int v12; // ebp
  unsigned int FirstTag; // eax
  unsigned int v14; // ebx
  const wchar_t *StringTagPtr; // rsi
  const wchar_t *v16; // r14
  unsigned int v17; // eax
  __int64 v18; // rdi
  const wchar_t **v19; // rcx
  struct _MATCH_PLUGIN * near *v20; // rdi
  struct _MATCH_PLUGIN *v21; // r15
  __int64 v23; // [rsp+A0h] [rbp+18h] BYREF

  v23 = a3;
  if ( a4 && (v11 = a5) != 0 && (v12 = a7) != 0 )
  {
    LODWORD(v23) = 0;
    FirstTag = SdbFindFirstTag(a5, a7, 24577);
    if ( FirstTag )
    {
      StringTagPtr = (const wchar_t *)SdbGetStringTagPtr(v11, FirstTag);
      if ( StringTagPtr )
      {
        v16 = 0;
        v17 = SdbFindFirstTag(v11, v12, 24584);
        if ( !v17 || (v16 = (const wchar_t *)SdbGetStringTagPtr(v11, v17)) != 0 )
        {
          v18 = 0;
          while ( 1 )
          {
            v19 = (const wchar_t **)(&g_MatchPlugins)[v18];
            if ( v19 )
            {
              if ( !wcsicmp(*v19, StringTagPtr) )
                break;
            }
            if ( (unsigned __int64)++v18 >= 0x18 )
              goto LABEL_15;
          }
          v20 = (&g_MatchPlugins)[v18];
          if ( !v20 )
          {
LABEL_15:
            v14 = -2147023728;
            AslLogCallPrintf(1, "AcmMatchPluginExecuteInternal", 137, "Plugin not registered [%ls].", StringTagPtr);
            return v14;
          }
          v21 = v20[2];
          if ( v21 )
            AslLogCallPrintf(
              3,
              "AcmMatchPluginExecuteInternal",
              151,
              "Plugin has a PluginContext set [%ls].",
              StringTagPtr);
          else
            v21 = a9;
          if ( ((unsigned int (__fastcall *)(__int64 *, void *, struct _DB *, _QWORD, unsigned int, const wchar_t *, struct _MATCH_PLUGIN *))v20[1])(
                 &v23,
                 a4,
                 v11,
                 a6,
                 v12,
                 v16,
                 v21) )
          {
            v14 = 0;
            *a1 = v23;
          }
          else
          {
            v14 = -2147467259;
            AslLogCallPrintf(
              1,
              "AcmMatchPluginExecuteInternal",
              162,
              "Plugin returned failure [%ls: %ls]",
              StringTagPtr,
              v16);
          }
        }
        else
        {
          v14 = -2147023538;
          AslLogCallPrintf(1, "AcmMatchPluginExecuteInternal", 125, "Failed to read plugin command line.");
        }
      }
      else
      {
        v14 = -2147023538;
        AslLogCallPrintf(1, "AcmMatchPluginExecuteInternal", 112, "Failed to read plugin name.");
      }
    }
    else
    {
      v14 = -2147023538;
      AslLogCallPrintf(1, "AcmMatchPluginExecuteInternal", 105, "Failed to find plugin name.");
    }
  }
  else
  {
    v14 = -2147024809;
    AslLogCallPrintf(1, "AcmMatchPluginExecuteInternal", 83, "Invalid parameters");
  }
  return v14;
}

```

## disassembly

```asm
0x18004f020  mov     rax, rsp
0x18004f023  mov     [rax+18h], r8
0x18004f027  push    rbx
0x18004f028  push    rbp
0x18004f029  push    rsi
0x18004f02a  push    rdi
0x18004f02b  push    r12
0x18004f02d  push    r13
0x18004f02f  push    r14
0x18004f031  push    r15
0x18004f033  sub     rsp, 48h
0x18004f037  mov     r12, r9
0x18004f03a  mov     r13, rcx
0x18004f03d  test    r9, r9
0x18004f040  jz      loc_18004F1FE
0x18004f046  mov     rbx, [rsp+88h+arg_20]
0x18004f04e  test    rbx, rbx
0x18004f051  jz      loc_18004F1FE
0x18004f057  mov     ebp, [rsp+88h+arg_30]
0x18004f05e  test    ebp, ebp
0x18004f060  jz      loc_18004F1FE
0x18004f066  mov     r8d, 6001h
0x18004f06c  mov     dword ptr [rax+18h], 0
0x18004f073  mov     edx, ebp
0x18004f075  mov     rcx, rbx
0x18004f078  call    SdbFindFirstTag
0x18004f07d  test    eax, eax
0x18004f07f  jnz     short loc_18004F096
0x18004f081  mov     ebx, 8007054Eh
0x18004f086  lea     r9, aFailedToFindPl; "Failed to find plugin name."
0x18004f08d  lea     r8d, [rax+69h]
0x18004f091  jmp     loc_18004F210
0x18004f096  mov     edx, eax
0x18004f098  mov     rcx, rbx
0x18004f09b  call    SdbGetStringTagPtr
0x18004f0a0  mov     rsi, rax
0x18004f0a3  test    rax, rax
0x18004f0a6  jnz     short loc_18004F0BD
0x18004f0a8  mov     ebx, 8007054Eh
0x18004f0ad  lea     r9, aFailedToReadPl; "Failed to read plugin name."
0x18004f0b4  lea     r8d, [rax+70h]
0x18004f0b8  jmp     loc_18004F210
0x18004f0bd  mov     r8d, 6008h
0x18004f0c3  mov     edx, ebp
0x18004f0c5  mov     rcx, rbx
0x18004f0c8  xor     r14d, r14d
0x18004f0cb  call    SdbFindFirstTag
0x18004f0d0  test    eax, eax
0x18004f0d2  jz      short loc_18004F0FB
0x18004f0d4  mov     edx, eax
0x18004f0d6  mov     rcx, rbx
0x18004f0d9  call    SdbGetStringTagPtr
0x18004f0de  mov     r14, rax
0x18004f0e1  test    rax, rax
0x18004f0e4  jnz     short loc_18004F0FB
0x18004f0e6  mov     ebx, 8007054Eh
0x18004f0eb  lea     r9, aFailedToReadPl_0; "Failed to read plugin command line."
0x18004f0f2  lea     r8d, [rax+7Dh]
0x18004f0f6  jmp     loc_18004F210
0x18004f0fb  xor     edi, edi
0x18004f0fd  lea     r15, ?g_MatchPlugins@@3PAPEAU_MATCH_PLUGIN@@A; _MATCH_PLUGIN * near * g_MatchPlugins
0x18004f104  mov     rcx, [r15+rdi*8]
0x18004f108  test    rcx, rcx
0x18004f10b  jz      short loc_18004F11C
0x18004f10d  mov     rcx, [rcx]; String1
0x18004f110  mov     rdx, rsi; String2
0x18004f113  call    _wcsicmp
0x18004f118  test    eax, eax
0x18004f11a  jz      short loc_18004F152
0x18004f11c  inc     rdi
0x18004f11f  cmp     rdi, 18h
0x18004f123  jb      short loc_18004F0FD
0x18004f125  lea     r9, aPluginNotRegis; "Plugin not registered [%ls]."
0x18004f12c  mov     [rsp+88h+var_68], rsi
0x18004f131  mov     r8d, 89h
0x18004f137  lea     rdx, aAcmmatchplugin_0; "AcmMatchPluginExecuteInternal"
0x18004f13e  mov     ecx, 1
0x18004f143  mov     ebx, 80070490h
0x18004f148  call    AslLogCallPrintf
0x18004f14d  jmp     loc_18004F221
0x18004f152  mov     rdi, [r15+rdi*8]
0x18004f156  test    rdi, rdi
0x18004f159  jz      short loc_18004F125
0x18004f15b  mov     r15, [rdi+10h]
0x18004f15f  test    r15, r15
0x18004f162  jz      short loc_18004F189
0x18004f164  lea     r9, aPluginHasAPlug; "Plugin has a PluginContext set [%ls]."
0x18004f16b  mov     [rsp+88h+var_68], rsi
0x18004f170  mov     r8d, 97h
0x18004f176  lea     rdx, aAcmmatchplugin_0; "AcmMatchPluginExecuteInternal"
0x18004f17d  mov     ecx, 3
0x18004f182  call    AslLogCallPrintf
0x18004f187  jmp     short loc_18004F191
0x18004f189  mov     r15, [rsp+88h+arg_40]
0x18004f191  mov     r9d, [rsp+88h+arg_28]
0x18004f199  lea     rcx, [rsp+88h+arg_10]
0x18004f1a1  mov     rax, [rdi+8]
0x18004f1a5  mov     r8, rbx
0x18004f1a8  mov     [rsp+88h+var_58], r15
0x18004f1ad  mov     rdx, r12
0x18004f1b0  mov     [rsp+88h+var_60], r14
0x18004f1b5  mov     dword ptr [rsp+88h+var_68], ebp
0x18004f1b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f1be  test    eax, eax
0x18004f1c0  jnz     short loc_18004F1EF
0x18004f1c2  mov     [rsp+88h+var_60], r14
0x18004f1c7  lea     r9, aPluginReturned; "Plugin returned failure [%ls: %ls]"
0x18004f1ce  mov     r8d, 0A2h
0x18004f1d4  mov     [rsp+88h+var_68], rsi
0x18004f1d9  lea     rdx, aAcmmatchplugin_0; "AcmMatchPluginExecuteInternal"
0x18004f1e0  mov     ebx, 80004005h
0x18004f1e5  lea     ecx, [rax+1]
0x18004f1e8  call    AslLogCallPrintf
0x18004f1ed  jmp     short loc_18004F221
0x18004f1ef  mov     eax, dword ptr [rsp+88h+arg_10]
0x18004f1f6  xor     ebx, ebx
0x18004f1f8  mov     [r13+0], eax
0x18004f1fc  jmp     short loc_18004F221
0x18004f1fe  mov     ebx, 80070057h
0x18004f203  lea     r9, aInvalidParamet; "Invalid parameters"
0x18004f20a  mov     r8d, 53h ; 'S'
0x18004f210  lea     rdx, aAcmmatchplugin_0; "AcmMatchPluginExecuteInternal"
0x18004f217  mov     ecx, 1
0x18004f21c  call    AslLogCallPrintf
0x18004f221  mov     eax, ebx
0x18004f223  add     rsp, 48h
0x18004f227  pop     r15
0x18004f229  pop     r14
0x18004f22b  pop     r13
0x18004f22d  pop     r12
0x18004f22f  pop     rdi
0x18004f230  pop     rsi
0x18004f231  pop     rbp
0x18004f232  pop     rbx
0x18004f233  retn
```
