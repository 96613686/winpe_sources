# Threadpool::CreateInstance(std::unique_ptr<Threadpool,std::default_delete<Threadpool>> *)

- ea: `0x18001f224`
- end: `0x18001f2cb`
- name: `?CreateInstance@Threadpool@@SAJPEAV?$unique_ptr@VThreadpool@@U?$default_delete@VThreadpool@@@std@@@std@@@Z`
- size: `167`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180016e80`

## callees

- `0x180003860`
- `0x180003f7c`
- `0x1800121b4`
- `0x18001f1f0`
- `0x18001f224`
- `0x18001f2d4`

## import_xrefs

- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18001f2ac`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18001f2ac`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18001f278`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18001f278`

## string_xrefs

- `0x18001f26f`: `Threadpool::CreateInstance`
- `0x18001f2a0`: `Threadpool::CreateInstance`

## pseudocode

```c
__int64 __fastcall Threadpool::CreateInstance(__int64 *a1)
{
  Threadpool *v2; // rax
  Threadpool *v3; // rbx
  int v4; // eax
  unsigned int v5; // eax
  unsigned int v6; // ebx
  Threadpool *v8; // [rsp+38h] [rbp+10h] BYREF

  v2 = (Threadpool *)operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
  v3 = v2;
  if ( !v2 )
  {
    v8 = 0;
    v5 = ZTraceReportOriginationNoThis(-2147024882, "Threadpool::CreateInstance", 22);
    goto LABEL_6;
  }
  memset_0(v2, 0, 0x58u);
  v8 = v3;
  v4 = Threadpool::Initialize(v3);
  if ( v4 < 0 )
  {
    v5 = ZTraceReportPropagationNoThis(v4, "Threadpool::CreateInstance", 24);
LABEL_6:
    v6 = v5;
    goto LABEL_7;
  }
  v6 = 0;
  std::unique_ptr<Threadpool>::operator=<std::default_delete<Threadpool>,0>(a1, (__int64 *)&v8);
LABEL_7:
  std::unique_ptr<Threadpool>::~unique_ptr<Threadpool>(&v8);
  return v6;
}

```

## disassembly

```asm
0x18001f224  mov     [rsp+arg_0], rbx
0x18001f229  push    rdi
0x18001f22a  sub     rsp, 20h
0x18001f22e  mov     rdi, rcx
0x18001f231  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001f238  mov     ecx, 58h ; 'X'; unsigned __int64
0x18001f23d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001f242  mov     rbx, rax
0x18001f245  test    rax, rax
0x18001f248  jz      short loc_18001F291
0x18001f24a  xor     edx, edx; Val
0x18001f24c  lea     r8d, [rdx+58h]; Size
0x18001f250  mov     rcx, rax; void *
0x18001f253  call    memset_0
0x18001f258  mov     [rsp+28h+arg_8], rbx
0x18001f25d  mov     rcx, rbx; this
0x18001f260  call    ?Initialize@Threadpool@@AEAAJXZ; Threadpool::Initialize(void)
0x18001f265  test    eax, eax
0x18001f267  jns     short loc_18001F280
0x18001f269  mov     r8d, 18h
0x18001f26f  lea     rdx, aThreadpoolCrea; "Threadpool::CreateInstance"
0x18001f276  mov     ecx, eax
0x18001f278  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18001f27e  jmp     short loc_18001F2B2
0x18001f280  xor     ebx, ebx
0x18001f282  lea     rdx, [rsp+28h+arg_8]
0x18001f287  mov     rcx, rdi
0x18001f28a  call    ??$?4U?$default_delete@VThreadpool@@@std@@$0A@@?$unique_ptr@VThreadpool@@U?$default_delete@VThreadpool@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Threadpool>::operator=<std::default_delete<Threadpool>,0>(std::unique_ptr<Threadpool> &&)
0x18001f28f  jmp     short loc_18001F2B4
0x18001f291  mov     [rsp+28h+arg_8], 0
0x18001f29a  mov     r8d, 16h
0x18001f2a0  lea     rdx, aThreadpoolCrea; "Threadpool::CreateInstance"
0x18001f2a7  mov     ecx, 8007000Eh
0x18001f2ac  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x18001f2b2  mov     ebx, eax
0x18001f2b4  lea     rcx, [rsp+28h+arg_8]
0x18001f2b9  call    ??1?$unique_ptr@VThreadpool@@U?$default_delete@VThreadpool@@@std@@@std@@QEAA@XZ; std::unique_ptr<Threadpool>::~unique_ptr<Threadpool>(void)
0x18001f2be  mov     eax, ebx
0x18001f2c0  mov     rbx, [rsp+28h+arg_0]
0x18001f2c5  add     rsp, 20h
0x18001f2c9  pop     rdi
0x18001f2ca  retn
```
