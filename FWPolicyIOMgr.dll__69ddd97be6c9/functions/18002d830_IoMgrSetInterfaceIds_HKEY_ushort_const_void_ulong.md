# IoMgrSetInterfaceIds(HKEY__ *,ushort const *,void *,ulong)

- ea: `0x18002d830`
- end: `0x18002dafb`
- name: `?IoMgrSetInterfaceIds@@YAJPEAUHKEY__@@PEBGPEAXK@Z`
- size: `715`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, _QWORD *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003b94`
- `0x1800042c4`
- `0x18001e9ac`
- `0x18002d830`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002da2f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002da2f`
- `fwbase!FwFree` at `0x18002dae2`
- `fwbase!FwFree` at `0x18002dae2`
- `fwbase!FwAlloc` at `0x18002d9bd`
- `fwbase!FwAlloc` at `0x18002d9bd`
- `fwbase!FwRegDeleteValue` at `0x18002d8b6`
- `fwbase!FwRegDeleteValue` at `0x18002d953`
- `fwbase!FwRegDeleteValue` at `0x18002d8b6`
- `fwbase!FwRegDeleteValue` at `0x18002d953`
- `fwbase!FwRegSetString` at `0x18002daa2`
- `fwbase!FwRegSetString` at `0x18002daa2`

## pseudocode

```c
__int64 __fastcall IoMgrSetInterfaceIds(HKEY a1, const unsigned __int16 *a2, _QWORD *a3, unsigned int a4)
{
  LPCOLESTR v8; // rcx
  unsigned int v9; // r14d
  __int64 v10; // rdi
  int v11; // eax
  int v12; // ebx
  __int64 v13; // rdx
  __int64 v14; // r9
  unsigned __int64 v15; // r15
  unsigned int v16; // esi

  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 304, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  v9 = 0;
  v10 = 0;
  if ( !a1 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v8 = WPP_GLOBAL_Control;
  }
  if ( a3 )
  {
    if ( a4 >= 0x10 )
    {
      if ( a3[1] )
      {
        if ( *(_DWORD *)a3 )
        {
          if ( *(_DWORD *)a3 <= 0x40u )
          {
            v15 = (unsigned int)(39 * *(_DWORD *)a3);
            v10 = FwAlloc(2 * v15);
            if ( v10 )
            {
              v16 = 0;
              while ( v9 < *(_DWORD *)a3 )
              {
                if ( (unsigned __int64)v16 + 39 > v15 )
                  MicrosoftTelemetryAssertTriggeredNoArgs();
                if ( !StringFromGUID2((const GUID *const)(a3[1] + 16LL * v9), (LPOLESTR)(v10 + 2LL * v16), 39) )
                {
                  v12 = -2147418113;
                  v8 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
                  {
                    v13 = 311;
                    goto LABEL_53;
                  }
                  goto LABEL_55;
                }
                *(_WORD *)(v10 + 2LL * (v16 + 38)) = 44;
                v16 += 39;
                ++v9;
              }
              if ( v16 != (_DWORD)v15 )
                MicrosoftTelemetryAssertTriggeredNoArgs();
              if ( *(_WORD *)(v10 + 2LL * (v16 - 1)) != 44 )
                MicrosoftTelemetryAssertTriggeredNoArgs();
              *(_WORD *)(v10 + 2LL * (v16 - 1)) = 0;
              v12 = FwRegSetString(a1, 0, a2, v10);
              if ( v12 < 0 )
              {
                v8 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
                {
                  v13 = 312;
                  goto LABEL_53;
                }
              }
            }
            else
            {
              v12 = -2147024882;
              v8 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              {
                v13 = 310;
LABEL_53:
                v14 = (unsigned int)v12;
                goto LABEL_54;
              }
            }
          }
          else
          {
            v14 = 2147942487LL;
            v12 = -2147024809;
            if ( v8 != (LPCOLESTR)&WPP_GLOBAL_Control && (v8[14] & 1) != 0 )
            {
              v13 = 309;
              goto LABEL_54;
            }
          }
          goto LABEL_55;
        }
      }
      else if ( *(_DWORD *)a3 )
      {
        v14 = 2147942487LL;
        v12 = -2147024809;
        if ( v8 != (LPCOLESTR)&WPP_GLOBAL_Control && (v8[14] & 1) != 0 )
        {
          v13 = 307;
          goto LABEL_54;
        }
        goto LABEL_55;
      }
      v11 = FwRegDeleteValue(a1, 0, a2);
      v12 = v11;
      if ( v11 < 0 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v13 = 308;
          goto LABEL_13;
        }
      }
    }
    else
    {
      v14 = 2147942487LL;
      v12 = -2147024809;
      if ( v8 != (LPCOLESTR)&WPP_GLOBAL_Control && (v8[14] & 1) != 0 )
      {
        v13 = 306;
        goto LABEL_54;
      }
    }
  }
  else
  {
    if ( a4 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v11 = FwRegDeleteValue(a1, 0, a2);
    v12 = v11;
    if ( v11 < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v13 = 305;
LABEL_13:
        v14 = (unsigned int)v11;
LABEL_54:
        WPP_SF_d(*((_QWORD *)v8 + 2), v13, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, v14);
      }
    }
  }
LABEL_55:
  FwFree(v10);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18002d830  mov     [rsp+arg_8], rdx
0x18002d835  push    rbx
0x18002d836  push    rbp
0x18002d837  push    rsi
0x18002d838  push    rdi
0x18002d839  push    r12
0x18002d83b  push    r13
0x18002d83d  push    r14
0x18002d83f  push    r15
0x18002d841  sub     rsp, 28h
0x18002d845  mov     esi, r9d
0x18002d848  mov     rbx, r8
0x18002d84b  mov     r13, rdx
0x18002d84e  mov     rbp, rcx
0x18002d851  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d858  lea     r15, WPP_GLOBAL_Control
0x18002d85f  lea     r12, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18002d866  cmp     rcx, r15
0x18002d869  jz      short loc_18002D889
0x18002d86b  test    byte ptr [rcx+1Ch], 8
0x18002d86f  jz      short loc_18002D889
0x18002d871  mov     rcx, [rcx+10h]
0x18002d875  mov     edx, 130h
0x18002d87a  mov     r8, r12
0x18002d87d  call    WPP_SF_
0x18002d882  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d889  xor     r14d, r14d
0x18002d88c  mov     edi, r14d
0x18002d88f  test    rbp, rbp
0x18002d892  jnz     short loc_18002D8A0
0x18002d894  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002d899  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d8a0  test    rbx, rbx
0x18002d8a3  jnz     short loc_18002D8F0
0x18002d8a5  test    esi, esi
0x18002d8a7  jz      short loc_18002D8AE
0x18002d8a9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002d8ae  mov     r8, r13
0x18002d8b1  xor     edx, edx
0x18002d8b3  mov     rcx, rbp
0x18002d8b6  call    cs:__imp_FwRegDeleteValue
0x18002d8bc  mov     ebx, eax
0x18002d8be  test    eax, eax
0x18002d8c0  jns     loc_18002DADF
0x18002d8c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d8cd  cmp     rcx, r15
0x18002d8d0  jz      loc_18002DADF
0x18002d8d6  test    byte ptr [rcx+1Ch], 1
0x18002d8da  jz      loc_18002DADF
0x18002d8e0  mov     edx, 131h
0x18002d8e5  mov     r9d, eax
0x18002d8e8  mov     r8, r12
0x18002d8eb  jmp     loc_18002DAD6
0x18002d8f0  cmp     esi, 10h
0x18002d8f3  jnb     short loc_18002D918
0x18002d8f5  mov     r9d, 80070057h
0x18002d8fb  mov     ebx, r9d
0x18002d8fe  cmp     rcx, r15
0x18002d901  jz      loc_18002DADF
0x18002d907  test    byte ptr [rcx+1Ch], 1
0x18002d90b  jz      loc_18002DADF
0x18002d911  mov     edx, 132h
0x18002d916  jmp     short loc_18002D8E8
0x18002d918  cmp     [rbx+8], r14
0x18002d91c  jnz     short loc_18002D946
0x18002d91e  cmp     [rbx], r14d
0x18002d921  jz      short loc_18002D94B
0x18002d923  mov     r9d, 80070057h
0x18002d929  mov     ebx, r9d
0x18002d92c  cmp     rcx, r15
0x18002d92f  jz      loc_18002DADF
0x18002d935  test    byte ptr [rcx+1Ch], 1
0x18002d939  jz      loc_18002DADF
0x18002d93f  mov     edx, 133h
0x18002d944  jmp     short loc_18002D8E8
0x18002d946  cmp     [rbx], r14d
0x18002d949  jnz     short loc_18002D987
0x18002d94b  mov     r8, r13
0x18002d94e  xor     edx, edx
0x18002d950  mov     rcx, rbp
0x18002d953  call    cs:__imp_FwRegDeleteValue
0x18002d959  mov     ebx, eax
0x18002d95b  test    eax, eax
0x18002d95d  jns     loc_18002DADF
0x18002d963  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d96a  cmp     rcx, r15
0x18002d96d  jz      loc_18002DADF
0x18002d973  test    byte ptr [rcx+1Ch], 1
0x18002d977  jz      loc_18002DADF
0x18002d97d  mov     edx, 134h
0x18002d982  jmp     loc_18002D8E5
0x18002d987  cmp     dword ptr [rbx], 40h ; '@'
0x18002d98a  jbe     short loc_18002D9B2
0x18002d98c  mov     r9d, 80070057h
0x18002d992  mov     ebx, r9d
0x18002d995  cmp     rcx, r15
0x18002d998  jz      loc_18002DADF
0x18002d99e  test    byte ptr [rcx+1Ch], 1
0x18002d9a2  jz      loc_18002DADF
0x18002d9a8  mov     edx, 135h
0x18002d9ad  jmp     loc_18002D8E8
0x18002d9b2  imul    r15d, [rbx], 27h ; '''
0x18002d9b6  mov     r12d, r15d
0x18002d9b9  lea     rcx, [r15+r15]
0x18002d9bd  call    cs:__imp_FwAlloc
0x18002d9c3  mov     rdi, rax
0x18002d9c6  test    rax, rax
0x18002d9c9  jnz     short loc_18002D9FB
0x18002d9cb  mov     ebx, 8007000Eh
0x18002d9d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d9d7  lea     rax, WPP_GLOBAL_Control
0x18002d9de  cmp     rcx, rax
0x18002d9e1  jz      loc_18002DADF
0x18002d9e7  test    byte ptr [rcx+1Ch], 1
0x18002d9eb  jz      loc_18002DADF
0x18002d9f1  mov     edx, 136h
0x18002d9f6  jmp     loc_18002DACC
0x18002d9fb  mov     esi, r14d
0x18002d9fe  mov     r13d, 2Ch ; ','
0x18002da04  cmp     r14d, [rbx]
0x18002da07  jnb     short loc_18002DA74
0x18002da09  mov     r13d, esi
0x18002da0c  lea     rax, [r13+27h]
0x18002da10  cmp     rax, r12
0x18002da13  jbe     short loc_18002DA1A
0x18002da15  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002da1a  mov     ecx, r14d
0x18002da1d  lea     rdx, [rdi+r13*2]; lpsz
0x18002da21  shl     rcx, 4
0x18002da25  mov     r8d, 27h ; '''; cchMax
0x18002da2b  add     rcx, [rbx+8]; rguid
0x18002da2f  call    cs:__imp_StringFromGUID2
0x18002da35  test    eax, eax
0x18002da37  jz      short loc_18002DA4F
0x18002da39  lea     ecx, [rsi+26h]
0x18002da3c  mov     r13d, 2Ch ; ','
0x18002da42  mov     [rdi+rcx*2], r13w
0x18002da47  lea     esi, [rcx+1]
0x18002da4a  inc     r14d
0x18002da4d  jmp     short loc_18002DA04
0x18002da4f  mov     ebx, 8000FFFFh
0x18002da54  mov     rcx, cs:WPP_GLOBAL_Control
0x18002da5b  lea     rax, WPP_GLOBAL_Control
0x18002da62  cmp     rcx, rax
0x18002da65  jz      short loc_18002DADF
0x18002da67  test    byte ptr [rcx+1Ch], 1
0x18002da6b  jz      short loc_18002DADF
0x18002da6d  mov     edx, 137h
0x18002da72  jmp     short loc_18002DACC
0x18002da74  cmp     esi, r15d
0x18002da77  jz      short loc_18002DA7E
0x18002da79  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002da7e  lea     eax, [rsi-1]
0x18002da81  mov     ebx, eax
0x18002da83  cmp     [rdi+rax*2], r13w
0x18002da88  jz      short loc_18002DA8F
0x18002da8a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002da8f  mov     r8, [rsp+68h+arg_8]
0x18002da94  xor     eax, eax
0x18002da96  mov     r9, rdi
0x18002da99  mov     [rdi+rbx*2], ax
0x18002da9d  xor     edx, edx
0x18002da9f  mov     rcx, rbp
0x18002daa2  call    cs:__imp_FwRegSetString
0x18002daa8  mov     ebx, eax
0x18002daaa  test    eax, eax
0x18002daac  jns     short loc_18002DADF
0x18002daae  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dab5  lea     rax, WPP_GLOBAL_Control
0x18002dabc  cmp     rcx, rax
0x18002dabf  jz      short loc_18002DADF
0x18002dac1  test    byte ptr [rcx+1Ch], 1
0x18002dac5  jz      short loc_18002DADF
0x18002dac7  mov     edx, 138h
0x18002dacc  mov     r9d, ebx
0x18002dacf  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18002dad6  mov     rcx, [rcx+10h]
0x18002dada  call    WPP_SF_d
0x18002dadf  mov     rcx, rdi
0x18002dae2  call    cs:__imp_FwFree
0x18002dae8  mov     eax, ebx
0x18002daea  add     rsp, 28h
0x18002daee  pop     r15
0x18002daf0  pop     r14
0x18002daf2  pop     r13
0x18002daf4  pop     r12
0x18002daf6  pop     rdi
0x18002daf7  pop     rsi
0x18002daf8  pop     rbp
0x18002daf9  pop     rbx
0x18002dafa  retn
```
