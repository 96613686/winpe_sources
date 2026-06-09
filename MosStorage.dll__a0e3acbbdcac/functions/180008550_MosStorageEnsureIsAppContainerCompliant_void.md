# MosStorageEnsureIsAppContainerCompliant(void)

- ea: `0x180008550`
- end: `0x18000866b`
- name: `?MosStorageEnsureIsAppContainerCompliant@@YAJXZ`
- size: `283`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001c80`
- `0x180006c44`
- `0x180007000`
- `0x180008550`
- `0x18000cb1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000857e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000857e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008645`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008645`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180008630`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180008630`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800085e5`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800085e5`

## string_xrefs

- `0x180008627`: `MosStorageEnsureIsAppContainerCompliant`

## pseudocode

```c
__int64 MosStorageEnsureIsAppContainerCompliant(void)
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  __int64 v2; // r8
  unsigned int v3; // ebx
  int MapsPersistedRegString; // eax
  int v5; // r8d
  const OLECHAR *v6; // rcx
  LPCOLESTR lpsz[2]; // [rsp+30h] [rbp-40h] BYREF
  __int64 v9; // [rsp+40h] [rbp-30h]
  unsigned __int64 v10; // [rsp+48h] [rbp-28h]
  GUID pclsid; // [rsp+50h] [rbp-20h] BYREF

  EnterCriticalSection(&CriticalSection);
  v3 = 0;
  if ( qword_180018B48 )
  {
    *(_OWORD *)lpsz = 0;
    v9 = 0;
    v10 = 7;
    LOWORD(lpsz[0]) = 0;
    MapsPersistedRegString = RegUtils::GetMapsPersistedRegString(v1, v0, v2, (__int64)lpsz);
    if ( MapsPersistedRegString >= 0 )
    {
      if ( !v9 )
      {
LABEL_14:
        std::wstring::~wstring((char **)lpsz);
        goto LABEL_15;
      }
      pclsid = 0;
      v6 = (const OLECHAR *)lpsz;
      if ( v10 > 7 )
        v6 = lpsz[0];
      MapsPersistedRegString = CLSIDFromString(v6, &pclsid);
      if ( MapsPersistedRegString >= 0 )
      {
        if ( *(_QWORD *)&pclsid.Data1 != *(_QWORD *)((char *)qword_180018B48 + 1084) )
          goto LABEL_14;
        if ( *(_QWORD *)pclsid.Data4 != *(_QWORD *)((char *)qword_180018B48 + 1092) )
          goto LABEL_14;
        MapsPersistedRegString = EnsureStorageIsAppContainerCompliant((unsigned int *)qword_180018B48);
        if ( MapsPersistedRegString >= 0 )
          goto LABEL_14;
        v5 = 1199;
      }
      else
      {
        v5 = 1194;
      }
    }
    else
    {
      v5 = 1189;
    }
    v3 = ZTraceReportPropagationNoThis(MapsPersistedRegString, "MosStorageEnsureIsAppContainerCompliant", v5);
    goto LABEL_14;
  }
LABEL_15:
  LeaveCriticalSection(&CriticalSection);
  return v3;
}

```

## disassembly

```asm
0x180008550  mov     [rsp-8+arg_0], rbx
0x180008555  mov     [rsp-8+arg_8], rsi
0x18000855a  push    rbp
0x18000855b  mov     rbp, rsp
0x18000855e  sub     rsp, 70h
0x180008562  mov     rax, cs:__security_cookie
0x180008569  xor     rax, rsp
0x18000856c  mov     [rbp+var_10], rax
0x180008570  lea     rsi, CriticalSection
0x180008577  mov     [rbp+var_50], rsi
0x18000857b  mov     rcx, rsi; lpCriticalSection
0x18000857e  call    cs:__imp_EnterCriticalSection
0x180008584  mov     [rbp+var_48], 1
0x180008588  xor     ebx, ebx
0x18000858a  cmp     cs:qword_180018B48, rbx
0x180008591  jz      loc_180008642
0x180008597  xorps   xmm0, xmm0
0x18000859a  movups  xmmword ptr [rbp+lpsz], xmm0
0x18000859e  mov     [rbp+var_30], rbx
0x1800085a2  mov     [rbp+var_28], 7
0x1800085aa  xor     eax, eax
0x1800085ac  mov     word ptr [rbp+lpsz], ax
0x1800085b0  lea     r9, [rbp+lpsz]
0x1800085b4  call    ?GetMapsPersistedRegString@RegUtils@@SAJW4MapsRegKeys@@PEBG1PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegUtils::GetMapsPersistedRegString(MapsRegKeys,ushort const *,ushort const *,std::wstring *)
0x1800085b9  test    eax, eax
0x1800085bb  jns     short loc_1800085C5
0x1800085bd  mov     r8d, 4A5h
0x1800085c3  jmp     short loc_180008627
0x1800085c5  cmp     [rbp+var_30], 0
0x1800085ca  jz      short loc_180008638
0x1800085cc  xorps   xmm0, xmm0
0x1800085cf  movups  xmmword ptr [rbp+pclsid.Data1], xmm0
0x1800085d3  lea     rcx, [rbp+lpsz]
0x1800085d7  cmp     [rbp+var_28], 7
0x1800085dc  cmova   rcx, [rbp+lpsz]; lpsz
0x1800085e1  lea     rdx, [rbp+pclsid]; pclsid
0x1800085e5  call    cs:__imp_CLSIDFromString
0x1800085eb  test    eax, eax
0x1800085ed  jns     short loc_1800085F7
0x1800085ef  mov     r8d, 4AAh
0x1800085f5  jmp     short loc_180008627
0x1800085f7  mov     rcx, cs:qword_180018B48
0x1800085fe  mov     rax, qword ptr [rbp+pclsid.Data1]
0x180008602  cmp     rax, [rcx+43Ch]
0x180008609  jnz     short loc_180008638
0x18000860b  mov     rax, qword ptr [rbp+pclsid.Data4]
0x18000860f  cmp     rax, [rcx+444h]
0x180008616  jnz     short loc_180008638
0x180008618  call    EnsureStorageIsAppContainerCompliant
0x18000861d  test    eax, eax
0x18000861f  jns     short loc_180008638
0x180008621  mov     r8d, 4AFh
0x180008627  lea     rdx, aMosstorageensu_4; "MosStorageEnsureIsAppContainerCompliant"
0x18000862e  mov     ecx, eax
0x180008630  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180008636  mov     ebx, eax
0x180008638  lea     rcx, [rbp+lpsz]
0x18000863c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008641  nop
0x180008642  mov     rcx, rsi; lpCriticalSection
0x180008645  call    cs:__imp_LeaveCriticalSection
0x18000864b  mov     eax, ebx
0x18000864d  mov     rcx, [rbp+var_10]
0x180008651  xor     rcx, rsp; StackCookie
0x180008654  call    __security_check_cookie
0x180008659  lea     r11, [rsp+70h+var_s0]
0x18000865e  mov     rbx, [r11+10h]
0x180008662  mov     rsi, [r11+18h]
0x180008666  mov     rsp, r11
0x180008669  pop     rbp
0x18000866a  retn
```
