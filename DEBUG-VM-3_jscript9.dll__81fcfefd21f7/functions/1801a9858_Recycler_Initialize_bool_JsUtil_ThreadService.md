# Recycler::Initialize(bool,JsUtil::ThreadService *)

- ea: `0x1801a9858`
- end: `0x1801a9901`
- name: `?Initialize@Recycler@@QEAAX_NPEAVThreadService@JsUtil@@@Z`
- size: `169`
- prototype: `void __fastcall(Recycler *__hidden this, bool, struct JsUtil::ThreadService *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18004c2c0`

## callees

- `0x180110cfc`
- `0x1801a9858`
- `0x1801a9908`
- `0x1801a99c8`
- `0x1802544dc`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x1801a98b8`
- `KERNEL32!CreateEventW` at `0x1801a98b8`
- `KERNEL32!CloseHandle` at `0x1801a98da`
- `KERNEL32!CloseHandle` at `0x1801a98da`

## pseudocode

```c
void __fastcall Recycler::Initialize(Recycler *this, char a2, struct JsUtil::ThreadService *a3)
{
  __int64 v4; // rcx
  HANDLE *v5; // rdi

  *((_BYTE *)this + 12906) = 0;
  *((_BYTE *)this + 12902) = 1;
  *((_BYTE *)this + 12911) = a2 ^ 1;
  *((_BYTE *)this + 12912) = a2 ^ 1;
  if ( !(unsigned int)Recycler::IsConcurrentEnabled(this) )
  {
LABEL_7:
    Recycler::InitializeNonConcurrent(this);
    goto LABEL_8;
  }
  v5 = (HANDLE *)(v4 + 16144);
  if ( !JsUtil::ThreadService::HasCallback(a3) )
    *v5 = CreateEventW(0, 0, 0, 0);
  if ( !Recycler::InitializeConcurrent(this, a3) )
  {
    if ( *v5 )
    {
      CloseHandle(*v5);
      *v5 = 0;
    }
    goto LABEL_7;
  }
LABEL_8:
  *((_QWORD *)this + 68) = this;
}

```

## disassembly

```asm
0x1801a9858  mov     rax, rsp
0x1801a985b  mov     [rax+20h], rbx
0x1801a985f  mov     [rax+18h], r8
0x1801a9863  mov     [rax+10h], dl
0x1801a9866  mov     [rax+8], rcx
0x1801a986a  push    rdi
0x1801a986b  sub     rsp, 20h
0x1801a986f  mov     al, dl
0x1801a9871  mov     byte ptr [rcx+326Ah], 0
0x1801a9878  xor     al, 1
0x1801a987a  mov     byte ptr [rcx+3266h], 1
0x1801a9881  mov     [rcx+326Fh], al
0x1801a9887  mov     rbx, rcx
0x1801a988a  mov     [rcx+3270h], al
0x1801a9890  call    ?IsConcurrentEnabled@Recycler@@AEBAHXZ; Recycler::IsConcurrentEnabled(void)
0x1801a9895  test    eax, eax
0x1801a9897  jz      short loc_1801A98E7
0x1801a9899  lea     rdi, [rcx+3F10h]
0x1801a98a0  mov     rcx, [rsp+28h+arg_10]; this
0x1801a98a5  call    ?HasCallback@ThreadService@JsUtil@@QEBA_NXZ; JsUtil::ThreadService::HasCallback(void)
0x1801a98aa  test    al, al
0x1801a98ac  jnz     short loc_1801A98C1
0x1801a98ae  xor     r9d, r9d; lpName
0x1801a98b1  xor     r8d, r8d; bInitialState
0x1801a98b4  xor     edx, edx; bManualReset
0x1801a98b6  xor     ecx, ecx; lpEventAttributes
0x1801a98b8  call    cs:__imp_CreateEventW
0x1801a98be  mov     [rdi], rax
0x1801a98c1  mov     rdx, [rsp+28h+arg_10]; struct JsUtil::ThreadService *
0x1801a98c6  mov     rcx, rbx; this
0x1801a98c9  call    ?InitializeConcurrent@Recycler@@AEAA_NPEAVThreadService@JsUtil@@@Z; Recycler::InitializeConcurrent(JsUtil::ThreadService *)
0x1801a98ce  test    al, al
0x1801a98d0  jnz     short loc_1801A98EF
0x1801a98d2  mov     rcx, [rdi]; hObject
0x1801a98d5  test    rcx, rcx
0x1801a98d8  jz      short loc_1801A98E7
0x1801a98da  call    cs:__imp_CloseHandle
0x1801a98e0  mov     qword ptr [rdi], 0
0x1801a98e7  mov     rcx, rbx; this
0x1801a98ea  call    ?InitializeNonConcurrent@Recycler@@AEAAXXZ; Recycler::InitializeNonConcurrent(void)
0x1801a98ef  mov     [rbx+220h], rbx
0x1801a98f6  mov     rbx, [rsp+28h+arg_18]
0x1801a98fb  add     rsp, 20h
0x1801a98ff  pop     rdi
0x1801a9900  retn
```
