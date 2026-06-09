# std::_Future_error_category2::message(int)

- ea: `0x180013020`
- end: `0x180013081`
- name: `?message@_Future_error_category2@std@@UEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@H@Z`
- size: `97`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000f3a0`
- `0x180013020`

## import_xrefs

- `msvcp_win!?_Syserror_map@std@@YAPEBDH@Z` at `0x180013043`
- `msvcp_win!?_Syserror_map@std@@YAPEBDH@Z` at `0x180013043`

## string_xrefs

- `0x180013060`: `future already retrieved`
- `0x180013057`: `promise already satisfied`

## pseudocode

```c
__int64 __fastcall std::_Future_error_category2::message(__int64 a1, __int64 a2, int a3)
{
  const char *v4; // rdx

  switch ( a3 )
  {
    case 1:
      v4 = "broken promise";
      break;
    case 2:
      v4 = "future already retrieved";
      break;
    case 3:
      v4 = "promise already satisfied";
      break;
    case 4:
      v4 = "no state";
      break;
    default:
      v4 = std::_Syserror_map(a3);
      break;
  }
  std::string::string(a2, v4);
  return a2;
}

```

## disassembly

```asm
0x180013020  push    rbx
0x180013022  sub     rsp, 30h
0x180013026  mov     ecx, r8d
0x180013029  mov     rbx, rdx
0x18001302c  sub     ecx, 1
0x18001302f  jz      short loc_180013069
0x180013031  sub     ecx, 1
0x180013034  jz      short loc_180013060
0x180013036  sub     ecx, 1
0x180013039  jz      short loc_180013057
0x18001303b  cmp     ecx, 1
0x18001303e  jz      short loc_18001304E
0x180013040  mov     ecx, r8d
0x180013043  call    cs:__imp_?_Syserror_map@std@@YAPEBDH@Z; std::_Syserror_map(int)
0x180013049  mov     rdx, rax
0x18001304c  jmp     short loc_180013070
0x18001304e  lea     rdx, aNoState; "no state"
0x180013055  jmp     short loc_180013070
0x180013057  lea     rdx, aPromiseAlready; "promise already satisfied"
0x18001305e  jmp     short loc_180013070
0x180013060  lea     rdx, aFutureAlreadyR; "future already retrieved"
0x180013067  jmp     short loc_180013070
0x180013069  lea     rdx, aBrokenPromise; "broken promise"
0x180013070  mov     rcx, rbx
0x180013073  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180013078  mov     rax, rbx
0x18001307b  add     rsp, 30h
0x18001307f  pop     rbx
0x180013080  retn
```
