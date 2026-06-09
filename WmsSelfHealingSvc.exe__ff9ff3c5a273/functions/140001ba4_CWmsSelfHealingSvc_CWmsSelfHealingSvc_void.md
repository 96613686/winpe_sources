# CWmsSelfHealingSvc::~CWmsSelfHealingSvc(void)

- ea: `0x140001ba4`
- end: `0x140001c71`
- name: `??1CWmsSelfHealingSvc@@UEAA@XZ`
- size: `205`
- prototype: `void __fastcall(CWmsSelfHealingSvc *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140001c80`
- `0x140003218`

## callees

- `0x140001ba4`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140001bc8`
- `KERNEL32!CloseHandle` at `0x140001bea`
- `KERNEL32!CloseHandle` at `0x140001c0c`
- `KERNEL32!CloseHandle` at `0x140001c2e`
- `KERNEL32!CloseHandle` at `0x140001c50`
- `KERNEL32!CloseHandle` at `0x140001bc8`
- `KERNEL32!CloseHandle` at `0x140001bea`
- `KERNEL32!CloseHandle` at `0x140001c0c`
- `KERNEL32!CloseHandle` at `0x140001c2e`
- `KERNEL32!CloseHandle` at `0x140001c50`

## pseudocode

```c
void __fastcall CWmsSelfHealingSvc::~CWmsSelfHealingSvc(CWmsSelfHealingSvc *this)
{
  char *v2; // rcx
  char *v3; // rcx
  char *v4; // rcx
  char *v5; // rcx
  char *v6; // rcx

  *(_QWORD *)this = &CWmsSelfHealingSvc::`vftable';
  v2 = (char *)*((_QWORD *)this + 106);
  if ( (unsigned __int64)(v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 106) = 0;
  }
  v3 = (char *)*((_QWORD *)this + 107);
  if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v3);
    *((_QWORD *)this + 107) = 0;
  }
  v4 = (char *)*((_QWORD *)this + 110);
  if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v4);
    *((_QWORD *)this + 110) = 0;
  }
  v5 = (char *)*((_QWORD *)this + 111);
  if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v5);
    *((_QWORD *)this + 111) = 0;
  }
  v6 = (char *)*((_QWORD *)this + 108);
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v6);
    *((_QWORD *)this + 108) = 0;
  }
  *(_QWORD *)this = &CNTService::`vftable';
}

```

## disassembly

```asm
0x140001ba4  push    rbx
0x140001ba6  sub     rsp, 20h
0x140001baa  lea     rax, ??_7CWmsSelfHealingSvc@@6B@; const CWmsSelfHealingSvc::`vftable'
0x140001bb1  mov     rbx, rcx
0x140001bb4  mov     [rcx], rax
0x140001bb7  mov     rcx, [rcx+350h]; hObject
0x140001bbe  lea     rax, [rcx-1]
0x140001bc2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140001bc6  ja      short loc_140001BD9
0x140001bc8  call    cs:__imp_CloseHandle
0x140001bce  mov     qword ptr [rbx+350h], 0
0x140001bd9  mov     rcx, [rbx+358h]; hObject
0x140001be0  lea     rax, [rcx-1]
0x140001be4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140001be8  ja      short loc_140001BFB
0x140001bea  call    cs:__imp_CloseHandle
0x140001bf0  mov     qword ptr [rbx+358h], 0
0x140001bfb  mov     rcx, [rbx+370h]; hObject
0x140001c02  lea     rax, [rcx-1]
0x140001c06  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140001c0a  ja      short loc_140001C1D
0x140001c0c  call    cs:__imp_CloseHandle
0x140001c12  mov     qword ptr [rbx+370h], 0
0x140001c1d  mov     rcx, [rbx+378h]; hObject
0x140001c24  lea     rax, [rcx-1]
0x140001c28  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140001c2c  ja      short loc_140001C3F
0x140001c2e  call    cs:__imp_CloseHandle
0x140001c34  mov     qword ptr [rbx+378h], 0
0x140001c3f  mov     rcx, [rbx+360h]; hObject
0x140001c46  lea     rax, [rcx-1]
0x140001c4a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140001c4e  ja      short loc_140001C61
0x140001c50  call    cs:__imp_CloseHandle
0x140001c56  mov     qword ptr [rbx+360h], 0
0x140001c61  lea     rax, ??_7CNTService@@6B@; const CNTService::`vftable'
0x140001c68  mov     [rbx], rax
0x140001c6b  add     rsp, 20h
0x140001c6f  pop     rbx
0x140001c70  retn
```
