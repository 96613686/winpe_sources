# GetCachedCurrentStorageDevice

- ea: `0x18000764c`
- end: `0x180007714`
- name: `GetCachedCurrentStorageDevice`
- size: `200`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180008ab0`
- `0x180008d20`
- `0x180009370`

## callees

- `0x180001c80`
- `0x18000733c`
- `0x18000764c`
- `0x18000e7ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007682`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007682`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800076e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800076e7`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x1800076bb`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x1800076bb`

## string_xrefs

- `0x1800076b2`: `GetCachedCurrentStorageDevice`

## pseudocode

```c
__int64 __fastcall GetCachedCurrentStorageDevice(void *a1)
{
  const void *v2; // rdx
  int CachedCurrentMapDataDirectory; // eax
  unsigned int v4; // ebx
  __int16 v6[264]; // [rsp+30h] [rbp-228h] BYREF

  EnterCriticalSection(&CriticalSection);
  v2 = qword_180018B48;
  if ( qword_180018B48 )
  {
LABEL_6:
    v4 = 0;
    memcpy_0(a1, v2, 0x670u);
    goto LABEL_7;
  }
  CachedCurrentMapDataDirectory = GetCachedCurrentMapDataDirectory(v6, 0x104u);
  if ( CachedCurrentMapDataDirectory >= 0 )
  {
    v2 = qword_180018B48;
    if ( !qword_180018B48 )
      __int2c();
    goto LABEL_6;
  }
  v4 = ZTraceReportPropagationNoThis(CachedCurrentMapDataDirectory, "GetCachedCurrentStorageDevice", 466);
LABEL_7:
  LeaveCriticalSection(&CriticalSection);
  return v4;
}

```

## disassembly

```asm
0x18000764c  mov     [rsp+arg_8], rbx
0x180007651  mov     [rsp+arg_10], rsi
0x180007656  push    rdi
0x180007657  sub     rsp, 250h
0x18000765e  mov     rax, cs:__security_cookie
0x180007665  xor     rax, rsp
0x180007668  mov     [rsp+258h+var_18], rax
0x180007670  mov     rdi, rcx
0x180007673  lea     rsi, CriticalSection
0x18000767a  mov     [rsp+258h+var_238], rsi
0x18000767f  mov     rcx, rsi; lpCriticalSection
0x180007682  call    cs:__imp_EnterCriticalSection
0x180007688  mov     [rsp+258h+var_230], 1
0x18000768d  mov     rdx, cs:qword_180018B48
0x180007694  test    rdx, rdx
0x180007697  jnz     short loc_1800076D3
0x180007699  mov     edx, 104h
0x18000769e  lea     rcx, [rsp+258h+var_228]
0x1800076a3  call    GetCachedCurrentMapDataDirectory
0x1800076a8  test    eax, eax
0x1800076aa  jns     short loc_1800076C5
0x1800076ac  mov     r8d, 1D2h
0x1800076b2  lea     rdx, aGetcachedcurre_0; "GetCachedCurrentStorageDevice"
0x1800076b9  mov     ecx, eax
0x1800076bb  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x1800076c1  mov     ebx, eax
0x1800076c3  jmp     short loc_1800076E4
0x1800076c5  mov     rdx, cs:qword_180018B48; Src
0x1800076cc  test    rdx, rdx
0x1800076cf  jnz     short loc_1800076D3
0x1800076d1  int     2Ch; Windows NT - assertion failure
0x1800076d3  xor     ebx, ebx
0x1800076d5  mov     rcx, rdi; void *
0x1800076d8  mov     r8d, 670h; Size
0x1800076de  call    memcpy_0
0x1800076e3  nop
0x1800076e4  mov     rcx, rsi; lpCriticalSection
0x1800076e7  call    cs:__imp_LeaveCriticalSection
0x1800076ed  mov     eax, ebx
0x1800076ef  mov     rcx, [rsp+258h+var_18]
0x1800076f7  xor     rcx, rsp; StackCookie
0x1800076fa  call    __security_check_cookie
0x1800076ff  lea     r11, [rsp+258h+var_8]
0x180007707  mov     rbx, [r11+18h]
0x18000770b  mov     rsi, [r11+20h]
0x18000770f  mov     rsp, r11
0x180007712  pop     rdi
0x180007713  retn
```
