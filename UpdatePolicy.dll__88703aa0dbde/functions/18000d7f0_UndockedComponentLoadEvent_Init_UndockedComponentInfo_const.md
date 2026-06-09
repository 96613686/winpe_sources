# UndockedComponentLoadEvent::Init(UndockedComponentInfo const &)

- ea: `0x18000d7f0`
- end: `0x18000d902`
- name: `?Init@UndockedComponentLoadEvent@@QEAAJAEBUUndockedComponentInfo@@@Z`
- size: `274`
- prototype: `int(UndockedComponentLoadEvent *__hidden this, const struct UndockedComponentInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180003128`

## callees

- `0x180006858`
- `0x18000a150`
- `0x18000d7f0`
- `0x18000e370`

## pseudocode

```c
__int64 __fastcall UndockedComponentLoadEvent::Init(
        UndockedComponentLoadEvent *this,
        const struct UndockedComponentInfo *a2)
{
  _QWORD *v2; // rbx
  void *v5; // rcx
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  int v13; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (_QWORD *)((char *)this + 16);
  *((_DWORD *)this + 2) = *(_DWORD *)a2;
  *((_DWORD *)this + 3) = *((_DWORD *)a2 + 1);
  v5 = (void *)*((_QWORD *)this + 2);
  if ( v5 )
  {
    SusFree(v5);
    *v2 = 0;
  }
  v6 = DuplicateOptionalString<wchar_t *,wchar_t *>(*((_QWORD *)a2 + 1), v2);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v9 = (void *)*((_QWORD *)this + 3);
    if ( v9 )
    {
      SusFree(v9);
      *((_QWORD *)this + 3) = 0;
    }
    v6 = DuplicateOptionalString<wchar_t *,wchar_t *>(*((_QWORD *)a2 + 2), (char *)this + 24);
    v7 = v6;
    if ( v6 >= 0 )
    {
      v10 = (void *)*((_QWORD *)this + 5);
      if ( v10 )
      {
        SusFree(v10);
        *((_QWORD *)this + 5) = 0;
      }
      v6 = DuplicateOptionalString<wchar_t *,wchar_t *>(*((_QWORD *)a2 + 4), (char *)this + 40);
      v7 = v6;
      if ( v6 >= 0 )
      {
        v11 = (void *)*((_QWORD *)this + 4);
        if ( v11 )
        {
          SusFree(v11);
          *((_QWORD *)this + 4) = 0;
        }
        v6 = DuplicateOptionalString<wchar_t *,wchar_t *>(*((_QWORD *)a2 + 3), (char *)this + 32);
        v7 = v6;
        if ( v6 >= 0 )
          return 0;
        v8 = 59;
      }
      else
      {
        v8 = 58;
      }
    }
    else
    {
      v8 = 57;
    }
  }
  else
  {
    v8 = 56;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\UndockingTelemetry\\UndockingTelemetry.cpp",
    (const char *)(unsigned int)v6,
    v13);
  return v7;
}

```

## disassembly

```asm
0x18000d7f0  mov     [rsp+arg_0], rbx
0x18000d7f5  mov     [rsp+arg_8], rsi
0x18000d7fa  push    rdi; int
0x18000d7fb  sub     rsp, 20h
0x18000d7ff  mov     eax, [rdx]
0x18000d801  lea     rbx, [rcx+10h]
0x18000d805  mov     [rcx+8], eax
0x18000d808  mov     rsi, rcx
0x18000d80b  mov     eax, [rdx+4]
0x18000d80e  mov     rdi, rdx
0x18000d811  mov     [rcx+0Ch], eax
0x18000d814  mov     rcx, [rbx]; lpMem
0x18000d817  test    rcx, rcx
0x18000d81a  jz      short loc_18000D828
0x18000d81c  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18000d821  mov     qword ptr [rbx], 0
0x18000d828  mov     rcx, [rdi+8]
0x18000d82c  mov     rdx, rbx
0x18000d82f  call    ??$DuplicateOptionalString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateOptionalString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x18000d834  mov     ebx, eax
0x18000d836  test    eax, eax
0x18000d838  jns     short loc_18000D858
0x18000d83a  mov     edx, 38h ; '8'; void *
0x18000d83f  mov     rcx, [rsp+28h]; this
0x18000d844  lea     r8, aCW1SSrcClientL_1; "C:\\__w\\1\\s\\src\\Client\\lib\\Undock"...
0x18000d84b  mov     r9d, eax; char *
0x18000d84e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d853  jmp     loc_18000D8F0
0x18000d858  lea     rbx, [rsi+18h]
0x18000d85c  mov     rcx, [rbx]; lpMem
0x18000d85f  test    rcx, rcx
0x18000d862  jz      short loc_18000D870
0x18000d864  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18000d869  mov     qword ptr [rbx], 0
0x18000d870  mov     rcx, [rdi+10h]
0x18000d874  mov     rdx, rbx
0x18000d877  call    ??$DuplicateOptionalString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateOptionalString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x18000d87c  mov     ebx, eax
0x18000d87e  test    eax, eax
0x18000d880  jns     short loc_18000D889
0x18000d882  mov     edx, 39h ; '9'
0x18000d887  jmp     short loc_18000D83F
0x18000d889  lea     rbx, [rsi+28h]
0x18000d88d  mov     rcx, [rbx]; lpMem
0x18000d890  test    rcx, rcx
0x18000d893  jz      short loc_18000D8A1
0x18000d895  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18000d89a  mov     qword ptr [rbx], 0
0x18000d8a1  mov     rcx, [rdi+20h]
0x18000d8a5  mov     rdx, rbx
0x18000d8a8  call    ??$DuplicateOptionalString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateOptionalString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x18000d8ad  mov     ebx, eax
0x18000d8af  test    eax, eax
0x18000d8b1  jns     short loc_18000D8BA
0x18000d8b3  mov     edx, 3Ah ; ':'
0x18000d8b8  jmp     short loc_18000D83F
0x18000d8ba  lea     rbx, [rsi+20h]
0x18000d8be  mov     rcx, [rbx]; lpMem
0x18000d8c1  test    rcx, rcx
0x18000d8c4  jz      short loc_18000D8D2
0x18000d8c6  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18000d8cb  mov     qword ptr [rbx], 0
0x18000d8d2  mov     rcx, [rdi+18h]
0x18000d8d6  mov     rdx, rbx
0x18000d8d9  call    ??$DuplicateOptionalString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateOptionalString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x18000d8de  mov     ebx, eax
0x18000d8e0  test    eax, eax
0x18000d8e2  jns     short loc_18000D8EE
0x18000d8e4  mov     edx, 3Bh ; ';'
0x18000d8e9  jmp     loc_18000D83F
0x18000d8ee  xor     ebx, ebx
0x18000d8f0  mov     rsi, [rsp+28h+arg_8]
0x18000d8f5  mov     eax, ebx
0x18000d8f7  mov     rbx, [rsp+28h+arg_0]
0x18000d8fc  add     rsp, 20h
0x18000d900  pop     rdi
0x18000d901  retn
```
