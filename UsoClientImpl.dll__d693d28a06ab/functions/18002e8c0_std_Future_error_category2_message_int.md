# std::_Future_error_category2::message(int)

- ea: `0x18002e8c0`
- end: `0x18002e977`
- name: `?message@_Future_error_category2@std@@UEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@H@Z`
- size: `183`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18002e8c0`
- `0x180031ab0`

## string_xrefs

- `0x18002e93b`: `future already retrieved`
- `0x18002e932`: `promise already satisfied`

## pseudocode

```c
__int64 __fastcall std::_Future_error_category2::message(__int64 a1, __int64 a2, int a3)
{
  __int64 *v4; // rax
  const char *v5; // rdx
  __int64 v6; // r8

  switch ( a3 )
  {
    case 1:
      v5 = "broken promise";
LABEL_17:
      v6 = -1;
      *(_OWORD *)a2 = 0;
      *(_QWORD *)(a2 + 16) = 0;
      *(_QWORD *)(a2 + 24) = 0;
      do
        ++v6;
      while ( v5[v6] );
      goto LABEL_19;
    case 2:
      v5 = "future already retrieved";
      goto LABEL_17;
    case 3:
      v5 = "promise already satisfied";
      goto LABEL_17;
    case 4:
      v5 = "no state";
      goto LABEL_17;
  }
  v4 = &qword_18006D8A0;
  while ( *(_DWORD *)v4 != a3 )
  {
    v4 += 2;
    if ( v4 == (__int64 *)"*" )
    {
      v5 = "unknown error";
      goto LABEL_10;
    }
  }
  v5 = (const char *)v4[1];
LABEL_10:
  v6 = -1;
  *(_OWORD *)a2 = 0;
  *(_QWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 24) = 0;
  do
    ++v6;
  while ( v5[v6] );
LABEL_19:
  std::string::_Construct<1,char const *>(a2, v5, v6);
  return a2;
}

```

## disassembly

```asm
0x18002e8c0  push    rbx
0x18002e8c2  sub     rsp, 30h
0x18002e8c6  xor     r9d, r9d
0x18002e8c9  mov     ecx, r8d
0x18002e8cc  mov     rbx, rdx
0x18002e8cf  sub     ecx, 1
0x18002e8d2  jz      short loc_18002E944
0x18002e8d4  sub     ecx, 1
0x18002e8d7  jz      short loc_18002E93B
0x18002e8d9  sub     ecx, 1
0x18002e8dc  jz      short loc_18002E932
0x18002e8de  cmp     ecx, 1
0x18002e8e1  jz      short loc_18002E929
0x18002e8e3  lea     rax, qword_18006D8A0
0x18002e8ea  cmp     [rax], r8d
0x18002e8ed  jz      short loc_18002E908
0x18002e8ef  add     rax, 10h
0x18002e8f3  lea     rcx, asc_18006DD90; "*"
0x18002e8fa  cmp     rax, rcx
0x18002e8fd  jnz     short loc_18002E8EA
0x18002e8ff  lea     rdx, aUnknownError; "unknown error"
0x18002e906  jmp     short loc_18002E90C
0x18002e908  mov     rdx, [rax+8]
0x18002e90c  xorps   xmm0, xmm0
0x18002e90f  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002e913  movups  xmmword ptr [rbx], xmm0
0x18002e916  mov     [rbx+10h], r9
0x18002e91a  mov     [rbx+18h], r9
0x18002e91e  inc     r8
0x18002e921  cmp     [rdx+r8], r9b
0x18002e925  jnz     short loc_18002E91E
0x18002e927  jmp     short loc_18002E966
0x18002e929  lea     rdx, aNoState; "no state"
0x18002e930  jmp     short loc_18002E94B
0x18002e932  lea     rdx, aPromiseAlready; "promise already satisfied"
0x18002e939  jmp     short loc_18002E94B
0x18002e93b  lea     rdx, aFutureAlreadyR; "future already retrieved"
0x18002e942  jmp     short loc_18002E94B
0x18002e944  lea     rdx, aBrokenPromise; "broken promise"
0x18002e94b  xorps   xmm0, xmm0
0x18002e94e  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002e952  movups  xmmword ptr [rbx], xmm0
0x18002e955  mov     [rbx+10h], r9
0x18002e959  mov     [rbx+18h], r9
0x18002e95d  inc     r8
0x18002e960  cmp     [rdx+r8], r9b
0x18002e964  jnz     short loc_18002E95D
0x18002e966  mov     rcx, rbx
0x18002e969  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18002e96e  mov     rax, rbx
0x18002e971  add     rsp, 30h
0x18002e975  pop     rbx
0x18002e976  retn
```
