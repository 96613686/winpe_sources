# CTitleBar::_ComputeHitTestRects(void)

- ea: `0x180018e5c`
- end: `0x180018f52`
- name: `?_ComputeHitTestRects@CTitleBar@@AEAAXXZ`
- size: `246`
- prototype: `void __fastcall(CTitleBar *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180017a90`
- `0x180017b90`

## import_xrefs

- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x180018e7e`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x180018e8e`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x180018e9f`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x180018eb0`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x180018ec1`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x180018ed2`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x180018ee3`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x180018ef7`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x180018f08`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x180018f19`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x180018f2d`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x180018e7e`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x180018e8e`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x180018e9f`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x180018eb0`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x180018ec1`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x180018ed2`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x180018ee3`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x180018ef7`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x180018f08`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x180018f19`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x180018f2d`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x180018f4b`

## pseudocode

```c
void __fastcall CTitleBar::_ComputeHitTestRects(CTitleBar *this)
{
  struct tagRECT *v1; // rbx

  v1 = (struct tagRECT *)((char *)this + 1252);
  CopyRect((LPRECT)((char *)this + 1396), (const RECT *)((char *)this + 852));
  CopyRect(v1, (const RECT *)((char *)this + 900));
  CopyRect(v1 + 3, (const RECT *)((char *)this + 1012));
  CopyRect(v1 + 7, (const RECT *)((char *)this + 1140));
  CopyRect(v1 + 4, (const RECT *)((char *)this + 1044));
  CopyRect(v1 + 5, (const RECT *)((char *)this + 1076));
  CopyRect(v1 + 6, (const RECT *)((char *)this + 1108));
  CopyRect(v1 + 8, (const RECT *)((char *)this + 1172));
  CopyRect(v1 + 1, (const RECT *)((char *)this + 932));
  CopyRect(v1 + 2, (const RECT *)((char *)this + 964));
  CopyRect(v1 + 10, (const RECT *)((char *)this + 1204));
  CopyRect(v1 + 11, (const RECT *)((char *)this + 1220));
}

```

## disassembly

```asm
0x180018e5c  mov     [rsp+arg_0], rbx
0x180018e61  push    rdi
0x180018e62  sub     rsp, 20h
0x180018e66  lea     rbx, [rcx+4E4h]
0x180018e6d  mov     rdi, rcx
0x180018e70  lea     rdx, [rcx+354h]; lprcSrc
0x180018e77  lea     rcx, [rbx+90h]; lprcDst
0x180018e7e  call    cs:__imp_CopyRect
0x180018e84  lea     rdx, [rdi+384h]; lprcSrc
0x180018e8b  mov     rcx, rbx; lprcDst
0x180018e8e  call    cs:__imp_CopyRect
0x180018e94  lea     rdx, [rdi+3F4h]; lprcSrc
0x180018e9b  lea     rcx, [rbx+30h]; lprcDst
0x180018e9f  call    cs:__imp_CopyRect
0x180018ea5  lea     rdx, [rdi+474h]; lprcSrc
0x180018eac  lea     rcx, [rbx+70h]; lprcDst
0x180018eb0  call    cs:__imp_CopyRect
0x180018eb6  lea     rdx, [rdi+414h]; lprcSrc
0x180018ebd  lea     rcx, [rbx+40h]; lprcDst
0x180018ec1  call    cs:__imp_CopyRect
0x180018ec7  lea     rdx, [rdi+434h]; lprcSrc
0x180018ece  lea     rcx, [rbx+50h]; lprcDst
0x180018ed2  call    cs:__imp_CopyRect
0x180018ed8  lea     rdx, [rdi+454h]; lprcSrc
0x180018edf  lea     rcx, [rbx+60h]; lprcDst
0x180018ee3  call    cs:__imp_CopyRect
0x180018ee9  lea     rdx, [rdi+494h]; lprcSrc
0x180018ef0  lea     rcx, [rbx+80h]; lprcDst
0x180018ef7  call    cs:__imp_CopyRect
0x180018efd  lea     rdx, [rdi+3A4h]; lprcSrc
0x180018f04  lea     rcx, [rbx+10h]; lprcDst
0x180018f08  call    cs:__imp_CopyRect
0x180018f0e  lea     rdx, [rdi+3C4h]; lprcSrc
0x180018f15  lea     rcx, [rbx+20h]; lprcDst
0x180018f19  call    cs:__imp_CopyRect
0x180018f1f  lea     rdx, [rdi+4B4h]; lprcSrc
0x180018f26  lea     rcx, [rbx+0A0h]; lprcDst
0x180018f2d  call    cs:__imp_CopyRect
0x180018f33  lea     rdx, [rdi+4C4h]
0x180018f3a  lea     rcx, [rbx+0B0h]
0x180018f41  mov     rbx, [rsp+28h+arg_0]
0x180018f46  add     rsp, 20h
0x180018f4a  pop     rdi
0x180018f4b  jmp     cs:__imp_CopyRect
```
